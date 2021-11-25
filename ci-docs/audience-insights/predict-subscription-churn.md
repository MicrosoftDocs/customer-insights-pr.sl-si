---
title: Predvidevanje odpovedi naročnin
description: Predvidite, ali za stranko obstaja tveganje, da ne bo več uporabljala izdelkov ali storitev naročnine vašega podjetja.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f9397729d2f79d079b4dea2ee92d0823b6d987e4
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799747"
---
# <a name="subscription-churn-prediction-preview"></a>Predvidevanje izgube naročnine (predogled)

Predvidevanje izgube naročnine vam pomaga predvideti, ali za stranko obstaja tveganje, da ne bo več uporabljala izdelkov ali storitev naročnine vašega podjetja. Na strani **Obveščanje** > **Predvidevanja** lahko ustvarite novo predvidevanje izgube naročnine. Izberite **Moja predvidevanja**, da si ogledate druga predvidevanja, ki ste jih ustvarili.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Preizkusite vadnico za predvidevanje izgube naročnin z vzorčnimi podatki: [Vzorčni vodnik za predvidevanje izgube naročnin](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelujočega](permissions.md).
- Poslovno znanje, da lahko razumete, kaj izguba pomeni za vaše podjetje. Podpiramo časovno opredeljene definicije izgube, kar pomeni, da se stranka po določenem času po poteku naročnine šteje za izgubljeno.
- Podatki o vaših naročninah in njihovi zgodovini:
    - Identifikatorji naročnin za razlikovanje med naročninami.
    - Identifikatorji strank za povezovanje naročnin z vašimi strankami.
    - Datumi dogodkov naročnine, ki določajo začetne datume, končne datume in datume, na katere so se dogodki naročnine zgodili.
    - Podatki o naročnini, da določite, ali gre za ponavljajočo se naročnino in kako pogosto se obnavlja.
    - Za semantično podatkovno shemo za naročnine so potrebni naslednji podatki:
        - **ID naročnine:** enolični identifikator naročnine.
        - **Končni datum naročnine:** datum poteka naročnine za stranko.
        - **Začetni datum naročnine:** datum začetka naročnine za stranko.
        - **Datum transakcije:** datum, ko se je zgodila sprememba naročnine. Primer: stranka kupi ali prekliče naročnino.
        - **Ali gre za ponavljajočo se naročnino:** polje z logično vrednostjo »true« ali »false«, ki določa, ali se bo naročnina obnovila z istim ID-jem naročnine brez posredovanja stranke
        - **Pogostost ponovitve (v mesecih):** pri ponavljajočih se naročninah gre za obdobje, za katerega se bo naročnina podaljšala. Navedeno je v mesecih. Primer: letna naročnina, ki se za stranko vsako leto samodejno podaljša za dodatno leto, ima vrednost 12.
        - (Neobvezno) **Znesek naročnine:** Znesek valute, ki ga stranka plača za podaljšanje naročnine. Pomaga lahko prepoznati vzorce za različne ravni naročnin.
- Podatki o dejavnostih strank:
    - Identifikatorji dejavnosti za razlikovanje med dejavnostmi iste vrste.
    - Identifikatorji strank za preslikavo dejavnosti v stranke.
    - Podatki o dejavnosti, ki vsebujejo ime in datum dejavnosti.
    - Semantična podatkovna shema za dejavnosti stranke vključuje:
        - **Primarni ključ:** enolični identifikator dejavnosti. Primer: obisk spletnega mesta ali zapis o uporabi, ki prikazuje, da si je stranka ogledala epizodo TV-oddaje.
        - **Časovni žig:** datum in ura dogodka, ki ga je prepoznal primarni ključ.
        - **Dogodek:** ime dogodka, ki ga želite uporabiti. Primer: polje, imenovano »UserAction«, v storitvi pretakanja videov ima lahko vrednost »Ogledano«.
        - **Podrobnosti:** podrobni podatki o dogodku. Primer: polje, imenovano »ShowTitle«, v storitvi pretakanja videov ima lahko vrednost videoposnetka, ki si ga je stranka ogledala.
- Predlagane lastnosti podatkov:
    - Zadostni zgodovinski podatki: naročniški podatki za vsaj podvojeni časovni okvir. Po možnosti dve do tri leta naročniških podatkov.
    - Stanje naročnine: podatki vključujejo dejavne in nedejavne naročnine za vsako stranko, tako da ima en ID stranke več vnosov.
    - Število strank: vsaj 10 profilov strank, po možnosti več kot 1000 posameznih strank. Model bo propadel z manj kot 10 strankami in nezadostnimi zgodovinskimi podatki.
    - Popolnost podatkov: manj kot 20 % manjkajočih vrednosti v podatkovnem polju podane entitete.
   
   > [!NOTE]
   > Za 50 % strank, za katere želite izračunati možnost odpovedi naročnine, boste potrebovali vsaj dva zapisa dejavnosti.

## <a name="create-a-subscription-churn-prediction"></a>Ustvarjanje predvidevanja izgube naročnine

1. Pri vpogledih v občinstvo izberite **Obveščanje** > **Predvidevanja**.
1. Izberite ploščico **Model izgube naročnine (predogled)** in izberite **Uporabi ta model**.
   > [!div class="mx-imgBorder"]
   > ![Ploščica »Model izgube naročnine« z gumbom »Uporabi ta model«.](media/subscription-churn-usethismodel.PNG "Ploščica »Model izgube naročnine« z gumbom »Uporabi ta model«")

### <a name="name-model"></a>Ime modela

1. Navedite ime modela, da ga boste lahko razlikovali od drugih modelov.
1. Navedite ime izhodne entitete samo s črkami in številkami, brez presledkov. To je ime, ki ga bo uporabila entiteta modela. Nato izberite **Naprej**.

### <a name="define-customer-churn"></a>Določitev izgube strank

1. Vnesite število za možnost **Dnevi od konca naročnine**, da lahko vaše podjetje šteje, da je stranka v stanju izgube. To obdobje je običajno primerno za poslovne dejavnosti, kot so ponudbe ali druga tržna prizadevanja, ki poskušajo preprečiti izgubo stranke.
1. Vnesite število za možnost **Dnevi v prihodnosti za napoved možnosti izgube strank**, da nastavite časovno okno za napoved izgube. Tako lahko na primer izberete napoved možnosti izgube strank v naslednjih 90 dneh, da lahko temu prilagodite trženje z namenom obdržanja strank. Napovedovanje tveganja izgube za daljša ali krajša obdobja lahko oteži obravnavo dejavnikov v vašem profilu tveganja izgube, odvisno od vaših poslovnih potreb. Če želite nadaljevati, izberite **Naprej**.
   >[!TIP]
   > Kadar koli lahko izberete možnost **Shrani in zapri**, da shranite predvidevanje kot osnutek. Osnutek predvidevanja boste lahko našli na zavihku **Moja predvidevanja** za nadaljevanje.

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Izberite **Dodaj podatke** za **Zgodovina naročnine** in izberite entiteto, ki zagotavlja podatke o zgodovini naročnine, kot je opisano v [pogojih](#prerequisites).
1. Če spodnja polja niso izpolnjena, konfigurirajte odnos med entiteto zgodovine naročnine in entiteto stranke.
    1. Izberite **Entiteta zgodovine naročnine**.
    1. Izberite **Polje**, ki prepozna stranko v entiteti zgodovine naročnine. Povezovati se mora s primarnim ID-jem stranke vaše entitete stranke.
    1. Izberite **Entiteto stranke**, ki se ujema z vašo primarno entiteto stranke.
    1. Vnesite ime, ki opisuje odnos.
       > [!div class="mx-imgBorder"]
       > ![Stran z zgodovino naročnine prikazuje vzpostavljanje odnosa s stranko.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Stran z zgodovino naročnine prikazuje vzpostavljanje odnosa s stranko")
1. Izberite **Naprej**.
1. Preslikajte semantična polja v atribute v entiteti zgodovine naročnine in izberite **Shrani**. Za opise polj si oglejte [pogoje](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Stran z zgodovino naročnine prikazuje semantične atribute, preslikane v polja v izbrani entiteti zgodovine naročnine.](media/subscription-churn-subscriptionhistorymapping.PNG "Stran z zgodovino naročnine prikazuje semantične atribute, preslikane v polja v izbrani entiteti zgodovine naročnine")
1. Izberite **Dodaj podatke** za **Dejavnosti stranke** in izberite entiteto, ki zagotavlja podatke o dejavnosti stranke, kot je opisano v pogojih.
1. Izberite vrsto dejavnosti, ki se ujema z vrsto dejavnosti stranke, ki jo konfigurirate.  Izberite **Ustvari novo** in navedite ime, če ne vidite možnosti, ki se ujema z vrsto dejavnosti, ki jo potrebujete.
1. Konfigurirati boste morali odnos med entiteto dejavnosti vaše stranke in entiteto stranke.
    1. V tabeli dejavnosti stranke izberite polje, ki prepozna stranko, ki jo je mogoče neposredno povezati s primarnim ID-jem stranke entitete vaše stranke.
    1. Izberite entiteto stranke, ki se ujema z vašo primarno entiteto stranke.
    1. Vnesite ime, ki opisuje odnos.
1. Izberite **Naprej**.
1. Preslikajte semantična polja v atribute v entiteti dejavnosti stranke in izberite **Shrani**. Za opise polj si oglejte [pogoje](#prerequisites).
1. (Neobvezno) Če imate kakršne koli druge dejavnosti stranke, ki jih želite vključiti, ponovite zgornje korake.
   > [!div class="mx-imgBorder"]
   > ![Določite odnos entitete.](media/subscription-churn-customeractivitiesmapping.PNG "Stran z dejavnostmi stranke prikazuje semantične atribute, preslikane v polja v izbrani entiteti dejavnosti stranke")
1. Izberite **Naprej**.

### <a name="set-schedule-and-review-configuration"></a>Nastavitev razporeda in pregled konfiguracije

1. Nastavite frekvenco za prekvalifikacijo modela. Ta nastavitev je pomembna za posodobitev natančnosti predvidevanj, saj se novi podatki vnesejo v vpoglede v občinstvo. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.
1. Izberite **Naprej**.
1. Preglejte konfiguracijo. Na kateri koli del konfiguracije predvidevanja se lahko vrnete tako, da izberete možnost **Uredi** pod prikazano vrednostjo. Lahko pa izberete korak konfiguracije v prikazu napredovanja.
1. Če so vse vrednosti pravilno konfigurirane, izberite **Shrani in zaženi** za začetek postopka predvidevanja. Na zavihku **Moja predvidevanja** si lahko ogledate stanje svojih predvidevanj. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled stanja in rezultatov predvidevanj

1. Pojdite na zavihek **Moja predvidevanja** v možnosti **Obveščanje** > **Predvidevanja**.
   > [!div class="mx-imgBorder"]
   > ![Pogled strani »Moja predvidevanja«.](media/subscription-churn-mypredictions.PNG "Pogled strani »Moja predvidevanja«")
1. Izberite predvidevanje, ki ga želite pregledati.
   - **Ime predvidevanja:** ime predvidevanja, navedeno pri ustvarjanju.
   - **Vrsta predvidevanja:** vrsta modela, uporabljenega za predvidevanje
   - **Izhodna entiteta:** ime entitete za shranjevanje rezultatov predvidevanja. Entiteto s tem imenom lahko najdete v razdelku **Podatki** > **Entitete**.    
     V izhodni entiteti je vrednost *ChurnScore* predvidena verjetnost izgube, *IsChurn* pa binarna oznaka na podlagi vrednosti *ChurnScore* s pragom 0,5. Privzeti prag morda ne bo deloval za vaš scenarij. [Ustvarite nov segment](segments.md#create-a-new-segment) z želenim pragom.
   - **Predvideno polje:** to polje je izpolnjeno le za nekatere vrste predvidevanj in se ne uporablja pri predvidevanju izgube naročnine.
   - **Stanje:** trenutno stanje izvajanja predvidevanja.
        - **V čakalni vrsti:** predvidevanje trenutno čaka, da se začnejo izvajati drugi postopki.
        - **Osveževanje:** predvidevanje trenutno izvaja stopnjo »rezultat« obdelave, da ustvari rezultate, ki se bodo pretakali v izhodno entiteto.
        - **Ni uspelo:** predvidevanje ni uspelo. Za več podrobnosti izberite **Dnevniki**.
        - **Uspešno:** predvidevanje je uspelo. Izberite **Pogled** pod navpičnimi tremi pikami za pregled predvidevanja
   - **Urejeno:** datum, ko je bila spremenjena konfiguracija predvidevanja.
   - **Nazadnje osveženo:** datum, ko je predvidevanje osvežilo rezultate v izhodni entiteti.
1. Izberite navpične tri pike poleg predvidevanja, za katerega želite pregledati rezultate, in izberite **Pogled**.
   > [!div class="mx-imgBorder"]
   > ![Pogled možnosti v meniju z navpičnimi tremi pikami za predvidevanje, vključno z urejanjem, osveževanjem, pogledom, dnevniki in brisanjem.](media/subscription-churn-verticalellipses.PNG "Pogled možnosti v meniju z navpičnimi tremi pikami za predvidevanje, vključno z urejanjem, osveževanjem, pogledom, dnevniki in brisanjem")
1. Na strani z rezultati so trije primarni razdelki podatkov:
    1. **Učinkovitost modela za kvalifikacijo:** A, B ali C so možni rezultati. Ta rezultat kaže na učinkovitost predvidevanja in vam lahko pomaga pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti.
        - Rezultati se določijo na podlagi naslednjih pravil:
            - **A**, kadar model natančno napove vsaj 50 % vseh predvidevanj in kadar je odstotek točnih predvidevanj za izgubljene stranke večji od pretekle povprečne stopnje osipa za vsaj 10 % pretekle povprečne stopnje osipa.
            - **B**, kadar model natančno napove vsaj 50 % vseh predvidevanj in kadar je odstotek točnih predvidevanj za izgubljene stranke večji od pretekle povprečne stopnje osipa za največ 10 % pretekle povprečne stopnje osipa.
            - **C**, kadar model natančno napove manj kot 50 % vseh predvidevanj ali kadar je odstotek točnih predvidevanj za izgubljene stranke manjši od pretekle povprečne stopnje osipa.
               > [!div class="mx-imgBorder"]
               > ![Pogled na rezultat učinkovitosti modela.](media/subscription-churn-modelperformance.PNG "Pogled na rezultat učinkovitosti modela")
    1. **Verjetnost izgube (število strank):** skupine strank na podlagi predvidenega tveganja za izgubo. Ti podatki vam bodo lahko pozneje v pomoč, če boste želeli ustvariti segment strank z visokim tveganjem za izgubo. Takšni segmenti vam pomagajo razumeti, kako mora biti nastavljena vaša prekinitev za članstvo v segmentu.
       > [!div class="mx-imgBorder"]
       > ![Graf, ki prikazuje porazdelitev rezultatov izgube, razdeljen na obsege od 0 % do 100 %.](media/subscription-churn-resultdistribution.PNG "Graf, ki prikazuje porazdelitev rezultatov izgube, razdeljen na obsege od 0 % do 100 %")
    1. **Najvplivnejši dejavniki:** ob ustvarjanju predvidevanja se upošteva veliko dejavnikov. Za vsakega od dejavnikov je izračunan pomen za združena predvidevanja, ki jih ustvari model. Te dejavnike lahko uporabite za pomoč pri preverjanju rezultatov predvidevanja. Lahko pa te podatke uporabite pozneje za [ustvarjanje segmentov](segments.md), ki bi lahko pomagali vplivati na tveganje izgube strank.
       > [!div class="mx-imgBorder"]
       > ![Seznam, ki prikazuje vplivne dejavnike in njihov pomen za napovedovanje rezultata izgube.](media/subscription-churn-influentialfactors.PNG "Seznam, ki prikazuje vplivne dejavnike in njihov pomen za napovedovanje rezultata izgube")

## <a name="manage-predictions"></a>Upravljanje predvidevanj

Predvidevanja je mogoče optimizirati, zanje odpraviti napake, osvežiti ali izbrisati. Preglejte poročilo o uporabnosti vhodnih podatkov, če želite izvedeti, kako narediti predvidevanje hitrejše in zanesljivejše. Za več informacij glejte razdelek [Upravljanje predvidevanj](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
