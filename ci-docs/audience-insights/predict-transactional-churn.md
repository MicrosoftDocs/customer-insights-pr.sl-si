---
title: Predvidevanje izgub glede transakcij
description: Predvidite, ali za stranko obstaja tveganje, da ne bo več kupovala izdelkov ali storitev vašega podjetja.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906876"
---
# <a name="transactional-churn-prediction-preview"></a>Predvidevanje izgub glede transakcij (predogled)

Predvidevanje izgub glede transakcij pomaga predvideti, ali stranka v določenem časovnem obdobju ne bo več kupovala vaših izdelkov ali storitev. Ustvarite lahko nove napovedi izgub v razdelku **Obveščanje** > **Predvidevanja**. Izberite **Moja predvidevanja**, da si ogledate druga predvidevanja, ki ste jih ustvarili.

> [!TIP]
> Preizkusite vadnico za predvidevanje izgube glede transakcij z vzorčnimi podatki: [Vzorčni vodnik za predvidevanje izgube glede transakcij (predogled)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.
- Poslovno znanje, da lahko razumete, kaj izguba pomeni za vaše podjetje. Podpiramo časovne opredelitve izgub, kar pomeni, da se za izgubo stranke šteje, če določeno obdobje ni opravila nakupov.
- Podatki o vaših transakcijah/nakupih in njihovi zgodovini:
    - Identifikatorji transakcij za razlikovanje nakupov/transakcij.
    - Identifikatorji strank za prilagajanje transakcij vašim strankam.
    - Datumi transakcijskih dogodkov, ki določajo datume, ko je prišlo do transakcije.
    - Semantična podatkovna shema za nakupe/transakcije zahteva naslednje informacije:
        - **ID transakcije:** enolični identifikator nakupa ali transakcije.
        - **Datum transakcije:** datum nakupa ali transakcije.
        - **Vrednost transakcije:** znesek valute/številčna vrednost transakcije/postavke.
        - (Neobvezno) **Enolični ID izdelka:** ID kupljenega izdelka ali storitve, če so vaši podatki na ravni postavke.
        - (Neobvezno) **Ali je bila ta transakcija vračilo:** polje true/false, ki določa, ali je bila transakcija vračilo ali ne. Če je **vrednost transakcije** negativna, bomo te podatke uporabili tudi za sklepanje o vračilu.
- (Neobvezno) Podatki o dejavnostih strank:
    - Identifikatorji dejavnosti za razlikovanje med dejavnostmi iste vrste.
    - Identifikatorji strank za preslikavo dejavnosti v stranke.
    - Podatki o dejavnosti, ki vsebujejo ime in datum dejavnosti.
    - Semantična podatkovna shema za dejavnosti stranke vključuje:
        - **Primarni ključ:** enolični identifikator dejavnosti. Na primer, obisk spletnega mesta ali zapis uporabe, ki prikazuje, da je stranka preizkusila vzorec vašega izdelka.
        - **Časovni žig:** datum in ura dogodka, ki ga je prepoznal primarni ključ.
        - **Dogodek:** ime dogodka, ki ga želite uporabiti. Na primer, polje z imenom »UserAction« v trgovini z živili je lahko kupon, ki ga kupec uporabi.
        - **Podrobnosti:** podrobni podatki o dogodku. Na primer, polje z imenom »CouponValue« v trgovini z živili je lahko vrednost valute kupona.
- Predlagane lastnosti podatkov:
    - Zadostni zgodovinski podatki: transakcijski podatki za vsaj podvojeni časovni okvir. Po možnosti dve do tri leta naročniških podatkov. 
    - Več nakupov na stranko: v idealnem primeru vsaj dve transakciji na stranko.
    - Število strank: vsaj 10 profilov strank, po možnosti več kot 1000 posameznih strank. Model bo propadel z manj kot 10 strankami in nezadostnimi zgodovinskimi podatki.
    - Popolnost podatkov: manj kot 20 % manjkajočih vrednosti v podatkovnem polju podane entitete.

> [!NOTE]
> Za podjetja z visoko pogostnostjo nakupov strank (vsakih nekaj tednov) je priporočljivo izbrati krajši časovni okvir predvidevanja in definicijo izgube. Za nizko pogostnost nakupov (vsakih nekaj mesecev ali enkrat na leto) izberite daljši časovni okvir in definicijo izgube.

## <a name="create-a-transactional-churn-prediction"></a>Ustvarjanje predvidevanja o izgubi glede transakcij

1. V rešitvi Customer Insights pojdite na **Obveščanje** > **Predvidevanja**.

1. Izberite ploščico **Model izgube strank (predogled)** in izberite **Uporabi ta model**.
   
1. V podoknu **Model izgube strank** izberite **Transakcijski** in izberite **Začetek**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Posnetek zaslona z izbrano transakcijsko možnostjo v podoknu modela izgube strank.":::

### <a name="name-model"></a>Ime modela

1. Navedite ime modela, da ga boste lahko razlikovali od drugih modelov.

1. Navedite ime izhodne entitete samo s črkami in številkami, brez presledkov. To je ime, ki ga bo uporabila entiteta modela. 

1. Izberite **Naprej**.

### <a name="define-customer-churn"></a>Določitev izgube stranke

1. Nastavite časovno obdobje za napovedovanje izgube v polju **Prepoznajte stranke, ki jih lahko izgubite v naslednjem času:**. Na primer, v naslednjih 90 dneh predvidite tveganje za izgubo strank, da temu prilagodite vaša prizadevanja za uspešno trženje. Predvidevanje tveganja izgube za daljše ali krajše časovno obdobje lahko oteži obravnavo dejavnikov v vašem profilu tveganja izgub, vendar je to odvisno od vaših specifičnih poslovnih potreb. 
   >[!TIP]
   > Kadar koli lahko izberete možnost **Shrani in zapri**, da shranite predvidevanje kot osnutek. Osnutek predvidevanja boste lahko našli na zavihku **Moja predvidevanja** za nadaljevanje.

1. Vnesite število dni za določitev izgube v polju **Stranka je izgubljena, če ni opravila nakupov toliko časa:**. Na primer, če stranka v zadnjih 30 dneh ni opravila nobenega nakupa, se lahko šteje, da je izgubljena za vaše podjetje. 

1. Če želite nadaljevati, izberite **Naprej**.

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Izberite **Dodaj podatke** za **Zgodovina nakupov** in izberite entiteto, ki zagotavlja informacije o zgodovini transakcij/nakupov, kot je opisano pri [predpogojih](#prerequisites).

1. Preslikajte semantična polja v atribute v entiteti vaše zgodovine nakupov in izberite **Naprej**. Za opise polj si oglejte [pogoje](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Preslikajte semantična polja za entiteto nakupa.":::

1. Če spodnja polja niso izpolnjena, konfigurirajte razmerje med entiteto zgodovine nakupov in entiteto stranke.
    1. Izberite **Entiteta zgodovine nakupov**.
    1. Izberite **Polje**, ki prepozna kupca v entiteti zgodovine nakupov. Povezovati se mora s primarnim ID-jem stranke vaše entitete stranke.
    1. Izberite **Entiteto stranke**, ki se ujema z vašo primarno entiteto stranke.
    1. Vnesite ime, ki opisuje odnos.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Stran z zgodovino nakupov, ki prikazuje vzpostavitev odnosa s stranko.":::
   
1. Izberite **Naprej**.

1. Po želji izberite **Dodaj podatke** za **Dejavnosti strank**. Izberite entiteto, ki zagotavlja informacije o dejavnosti strank, kot je opisano v predpogojih.

1. Preslikajte semantična polja v atribute v entiteti dejavnosti strank in izberite **Naprej**. Za opise polj si oglejte [pogoje](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Preslikajte polja strank za podatke o transakciji.":::

1. Izberite vrsto dejavnosti, ki se ujema z vrsto dejavnosti stranke, ki jo konfigurirate. Izberite **Ustvari novo** in izberite razpoložljivo vrsto dejavnosti ali ustvarite novo vrsto.

1. Konfigurirati boste morali odnos med entiteto dejavnosti vaše stranke in entiteto stranke.
    1. Izberite polje, ki prepozna stranko v tabeli dejavnosti strank. Lahko je neposredno povezano s primarnim ID-jem stranke za vašo entiteto stranke.
    1. Izberite entiteto stranke, ki se ujema z vašo primarno entiteto stranke.
    1. Vnesite ime, ki opisuje odnos.

1. Izberite **Shrani**.

1. Če imate še kakšno dejavnost strank, ki bi jo radi vključili, ponovite zgornje korake.

1. Izberite **Naprej**.

### <a name="set-schedule-and-review-configuration"></a>Nastavitev razporeda in pregled konfiguracije

1. Nastavite frekvenco za prekvalifikacijo modela. Ta nastavitev je pomembna za posodobitev natančnosti predvidevanj, ko se vnesejo novi podatki. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

1. Preglejte konfiguracijo predvidevanja. Z izbiro možnosti **Uredi** se lahko vrnete na prejšnje korake pod prikazano vrednostjo. Lahko pa izberete korak konfiguracije v prikazu napredovanja.

1. Če so vse vrednosti pravilno konfigurirane, izberite **Shrani in zaženi** za začetek postopka predvidevanja. Na zavihku **Moja predvidevanja** si lahko ogledate stanje svojih predvidevanj. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

## <a name="review-a-prediction-status-and-results"></a>Pregled stanja in rezultatov predvidevanj

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite predvidevanje, ki ga želite pregledati.
   - **Ime predvidevanja:** ime predvidevanja, navedeno ob ustvarjanju.
   - **Vrsta predvidevanja:** vrsta modela, uporabljena za predvidevanje
   - **Izhodna entiteta:** ime entitete za shranjevanje rezultatov predvidevanja. Entiteto s tem imenom lahko najdete v razdelku **Podatki** > **Entitete**.    
     V izhodni entiteti je vrednost *ChurnScore* predvidena verjetnost izgube, *IsChurn* pa binarna oznaka na podlagi vrednosti *ChurnScore* s pragom 0,5. Privzeti prag morda ne bo deloval za vaš scenarij. [Ustvarite nov segment](segments.md#create-a-new-segment) z želenim pragom.
     Vse stranke niso nujno tudi dejavne stranke. Nekatere od njih morda že dolgo niso bile dejavne in se na podlagi definicije izgube že štejejo za izgubljene. Napovedovanje tveganja izgube za strank, ki so že izgubljene, ni koristno, ker ne spadajo v ciljno občinstvo.
   - **Predvideno polje:** to polje je zapolnjeno samo za nekatere vrste predvidevanj in se ne uporablja pri predvidevanju izgub.
   - **Stanje:** stanje izvajanja predvidevanja.
        - **V čakalni vrsti:** predvidevanje čaka, da se zaženejo drugi procesi.
        - **Osveževanje:** predvidevanje se trenutno izvaja za ustvarjanje rezultatov, ki bodo stekli v izhodno entiteto.
        - **Ni uspelo:** izvajanje predvidevanja ni uspelo. [Preglejte dnevniške datoteke](#troubleshoot-a-failed-prediction) za več podrobnosti.
        - **Uspelo:** predvidevanje je uspelo. Izberite **Pogled** pod navpičnimi tremi pikami za pregled predvidevanja
   - **Urejeno:** datum, ko je bila spremenjena konfiguracija predvidevanja.
   - **Nazadnje osveženo:** datum, ko je predvidevanje osvežilo rezultate v izhodni entiteti.

1. Izberite navpične tri pike poleg predvidevanja, za katerega želite pregledati rezultate, in izberite **Pogled**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Oglejte si kontrolnik, da vidite rezultate predvidevanja.":::   

1. Na strani z rezultati so trije primarni razdelki podatkov:
    1. **Učinkovitost modela za kvalifikacijo:** A, B ali C so možni rezultati. Ta rezultat kaže na učinkovitost predvidevanja in vam lahko pomaga pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti. Rezultati se določijo na podlagi naslednjih pravil:
         
         - **A**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, večji od izhodiščne stopnje za vsaj 10 %.
            
         - **B**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, do 10 % večji od izhodiščne stopnje.
            
         - **C**, ko je model natančno napovedal manj kot 50 % vseh predvidevanj ali ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, manjši od izhodiščne stopnje.
               
         - **Izhodišče** uporabi vnos časovnega obdobja predvidevanja za model (na primer eno leto) in model ustvari različne delce časa tako, da ga deli z 2, dokler ne doseže enega meseca ali manj. Te delce uporablja za ustvarjanje poslovnega pravila za stranke, ki niso opravile nakupa v tem časovnem okviru. Te stranke se štejejo za izgubljene. Kot izhodiščni model je izbrano časovno pravilo poslovanja z najvišjo zmožnostjo predvidevanja, kdo se bo verjetno izgubil.
            
    1. **Verjetnost izgube (število strank):** skupine strank na podlagi predvidenega tveganja za izgubo. Ti podatki vam bodo lahko pozneje v pomoč, če boste želeli ustvariti segment strank z visokim tveganjem za izgubo. Takšni segmenti vam pomagajo razumeti, kako mora biti nastavljena vaša prekinitev za članstvo v segmentu.
       
    1. **Najvplivnejši dejavniki:** ob ustvarjanju predvidevanja se upošteva veliko dejavnikov. Vsak od dejavnikov ima svoj pomen, izračunan za združena predvidevanja, ki jih ustvari model. Te dejavnike lahko uporabite za pomoč pri preverjanju rezultatov predvidevanja. Lahko pa te podatke uporabite pozneje za [ustvarjanje segmentov](segments.md), ki bi lahko pomagali vplivati na tveganje izgube strank.

## <a name="troubleshoot-a-failed-prediction"></a>Odpravite težave z neuspešnim predvidevanjem

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, za katere si želite ogledati dnevnike napak.

1. Izberite **Dnevniki**.

1. Preglejte vse napake. Pride lahko do več vrst napak, ki opisujejo, kakšno stanje je povzročilo napako. Primer: napaka, za katero ni dovolj podatkov za natančno predvidevanje, se običajno odpravi z nalaganjem dodatnih podatkov v storitev Customer Insights.

## <a name="refresh-a-prediction"></a>Osveževanje predvidevanja

Predvidevanja se bodo samodejno osvežila v istem [urniku, kot ga osvežijo vaši podatki](system.md#schedule-tab), ko se konfigurirajo v nastavitvah. Lahko jih osvežite tudi ročno.

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite osvežiti.

1. Izberite **Osveži**.

## <a name="delete-a-prediction"></a>Brisanje predvidevanja

Če izbrišete predvidevanje, odstranite tudi njegovo izhodno entiteto.

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg predvidevanja, ki ga želite izbrisati.

1. Izberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
