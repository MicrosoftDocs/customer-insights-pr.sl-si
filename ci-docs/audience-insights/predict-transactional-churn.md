---
title: Pretok transakcij predvidevanje (vsebuje video)
description: Predvidite, ali za stranko obstaja tveganje, da ne bo več kupovala izdelkov ali storitev vašega podjetja.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9aa208ad94dcb6b1e0f110a3f974c56de00bbd07
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355679"
---
# <a name="transaction-churn-prediction"></a>Predvidevanje izgube transakcij

Predvidevanje izgub glede transakcij pomaga predvideti, ali stranka v določenem časovnem obdobju ne bo več kupovala vaših izdelkov ali storitev. Ustvarite lahko nove napovedi izgub v razdelku **Obveščanje** > **Predvidevanja**. Izberite **Moja predvidevanja**, da si ogledate druga predvidevanja, ki ste jih ustvarili. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Za okolja, ki temeljijo na poslovnih računih, lahko predvidimo izgubo transakcij za račun in tudi kombinacijo računa in druge ravni informacij, kot je kategorija izdelkov. Če dodate dimenzijo, lahko ugotovite, kako verjetno je, da bo račun »Contoso« nehal kupovati kategorijo izdelkov »pisarniški material«. Poleg tega lahko za poslovne račune uporabimo tudi umetno inteligenco za ustvarjanje seznama možnih vzrokov, zakaj se bo račun verjetno izgubil za kategorijo podatkov sekundarne ravni.

> [!TIP]
> Preizkusite vadnico za odtok transakcij predvidevanje z uporabo vzorčnih podatkov: [Vzorčni vodnik za odtok transakcij predvidevanje](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Zahteve

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.
- Poslovno znanje, da lahko razumete, kaj izguba pomeni za vaše podjetje. Podpiramo časovne opredelitve izgub, kar pomeni, da se za izgubo stranke šteje, če določeno obdobje ni opravila nakupov.
- Podatki o vaših transakcijah/nakupih in njihovi zgodovini:
    - Identifikatorji transakcij za razlikovanje nakupov/transakcij.
    - Identifikatorji strank za prilagajanje transakcij vašim strankam.
    - Datumi transakcijskih dogodkov, ki določajo datume, ko je prišlo do transakcije.
    - Semantična podatkovna shema za nakupe/transakcije zahteva naslednje informacije:
        - **ID transakcije**: enolični identifikator nakupa ali transakcije.
        - **Datum transakcije**: datum nakupa ali transakcije.
        - **Vrednost transakcije**: znesek valute/številčna vrednost transakcije/postavke.
        - (Neobvezno) **Enolični ID izdelka**: ID kupljenega izdelka ali storitve, če so vaši podatki na ravni postavke.
        - (Neobvezno) **Ali je bila ta transakcija vračilo**: polje true/false, ki določa, ali je bila transakcija vračilo ali ne. Če je **vrednost transakcije** negativna, bomo te podatke uporabili tudi za sklepanje o vračilu.
- (Neobvezno) Podatki o dejavnostih strank:
    - Identifikatorji dejavnosti za razlikovanje med dejavnostmi iste vrste.
    - Identifikatorji strank za preslikavo dejavnosti v stranke.
    - Podatki o dejavnosti, ki vsebujejo ime in datum dejavnosti.
    - Semantična podatkovna shema za dejavnosti stranke vključuje:
        - **Primarni ključ:** enolični identifikator dejavnosti. Na primer, obisk spletnega mesta ali zapis uporabe, ki prikazuje, da je stranka preizkusila vzorec vašega izdelka.
        - **Časovni žig:** datum in ura dogodka, ki ga je prepoznal primarni ključ.
        - **Dogodek:** ime dogodka, ki ga želite uporabiti. Na primer, polje z imenom »UserAction« v trgovini z živili je lahko kupon, ki ga kupec uporabi.
        - **Podrobnosti:** podrobni podatki o dogodku. Na primer, polje z imenom »CouponValue« v trgovini z živili je lahko vrednost valute kupona.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.
- Poslovno znanje, da lahko razumete, kaj izguba pomeni za vaše podjetje. Podpiramo časovne opredelitve izgub, kar pomeni, da se za izgubo stranke šteje, če določeno obdobje ni opravila nakupov.
- Podatki o vaših transakcijah/nakupih in njihovi zgodovini:
    - Identifikatorji transakcij za razlikovanje nakupov/transakcij.
    - Identifikatorji strank za prilagajanje transakcij vašim strankam.
    - Datumi transakcijskih dogodkov, ki določajo datume, ko je prišlo do transakcije.
    - Semantična podatkovna shema za nakupe/transakcije zahteva naslednje informacije:
        - **ID transakcije**: enolični identifikator nakupa ali transakcije.
        - **Datum transakcije**: datum nakupa ali transakcije.
        - **Vrednost transakcije**: znesek valute/številčna vrednost transakcije/postavke.
        - (Neobvezno) **Enolični ID izdelka**: ID kupljenega izdelka ali storitve, če so vaši podatki na ravni postavke.
        - (Neobvezno) **Ali je bila ta transakcija vračilo**: polje true/false, ki določa, ali je bila transakcija vračilo ali ne. Če je **vrednost transakcije** negativna, bomo te podatke uporabili tudi za sklepanje o vračilu.
- (Neobvezno) Podatki o dejavnostih strank:
    - Identifikatorji dejavnosti za razlikovanje med dejavnostmi iste vrste.
    - Identifikatorji strank za preslikavo dejavnosti v stranke.
    - Podatki o dejavnosti, ki vsebujejo ime in datum dejavnosti.
    - Semantična podatkovna shema za dejavnosti stranke vključuje:
        - **Primarni ključ:** enolični identifikator dejavnosti. Na primer, obisk spletnega mesta ali zapis uporabe, ki prikazuje, da je stranka preizkusila vzorec vašega izdelka.
        - **Časovni žig:** datum in ura dogodka, ki ga je prepoznal primarni ključ.
        - **Dogodek:** ime dogodka, ki ga želite uporabiti. Na primer, polje z imenom »UserAction« v trgovini z živili je lahko kupon, ki ga kupec uporabi.
        - **Podrobnosti:** podrobni podatki o dogodku. Na primer, polje z imenom »CouponValue« v trgovini z živili je lahko vrednost valute kupona.
- (Izbirno) Podatki o vaših strankah:
    - Ti podatki bi se morali poravnati bolj statičnim atributom, da bi zagotovili najučinkovitejši model.
    - Shema semantičnih podatkov za podatke o strankah vključuje:
        - **CustomerID:** enolični identifikator za stranko.
        - **Datum nastanka:** datum, ko je bila stranka prvotno dodana.
        - **Država ali območje:** lokacija zvezne države ali območja stranke.
        - **Država:** država/regija stranke.
        - **Industrija:** vrsta panoge stranke. Na primer, polje, imenovano »Industrija« v pražilniku kave, lahko označuje, ali je bila stranka trgovina na drobno.
        - **Razvrstitev:** razvrščanje stranke za vaše podjetje. Na primer, polje, imenovano »ValueSegment« v pražilniku kave, je lahko raven stranke glede na velikost stranke.

---

- Predlagane lastnosti podatkov:
    - Zadostni zgodovinski podatki: transakcijski podatki za vsaj podvojeni časovni okvir. Po možnosti dve do tri leta zgodovine transakcij. 
    - Več nakupov na stranko: v idealnem primeru vsaj dve transakciji na stranko.
    - Število strank: vsaj 10 profilov strank, po možnosti več kot 1000 posameznih strank. Model bo propadel z manj kot 10 strankami in nezadostnimi zgodovinskimi podatki.
    - Popolnost podatkov: manj kot 20 % manjkajočih vrednosti v podatkovnem polju podane entitete.

> [!NOTE]
> Za podjetja z visoko pogostnostjo nakupov strank (vsakih nekaj tednov) je priporočljivo izbrati krajši časovni okvir predvidevanja in definicijo izgube. Za nizko pogostnost nakupov (vsakih nekaj mesecev ali enkrat na leto) izberite daljši časovni okvir in definicijo izgube.

## <a name="create-a-transaction-churn-prediction"></a>Ustvarjanje predvidevanja izgube transakcij

1. V rešitvi Customer Insights pojdite na **Obveščanje** > **Predvidevanja**.

1. Izberite **Model odliva strank** ploščico in izberite **Uporabite ta model**.

1. V podoknu **Model izgube strank** izberite **Transakcija** in nato **Začetek**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Posnetek zaslona z izbrano možnostjo transakcije v podoknu modela izgube strank.":::
 
### <a name="name-model"></a>Ime modela

1. Navedite ime modela, da ga boste lahko razlikovali od drugih modelov.

1. Navedite ime izhodne entitete samo s črkami in številkami, brez presledkov. To je ime, ki ga bo uporabila entiteta modela. 

1. Izberite **Naprej**.

### <a name="define-customer-churn"></a>Določitev izgube stranke

1. Nastavite **predvidevanje okno**. Na primer, v naslednjih 90 dneh predvidite tveganje za izgubo strank, da temu prilagodite vaša prizadevanja za uspešno trženje. Predvidevanje tveganja izgube za daljše ali krajše časovno obdobje lahko oteži obravnavo dejavnikov v vašem profilu tveganja izgub, vendar je to odvisno od vaših specifičnih poslovnih potreb.
   >[!TIP]
   > Lahko izberete **Shrani osnutek** kadar koli shranite predvidevanje kot osnutek. Osnutek predvidevanja boste lahko našli na zavihku **Moja predvidevanja** za nadaljevanje.

1. Vnesite število dni za določitev odliva v **Opredelitev odtoka** polje. Na primer, če stranka v zadnjih 30 dneh ni opravila nobenega nakupa, se lahko šteje, da je izgubljena za vaše podjetje. 

1. Če želite nadaljevati, izberite **Naprej**.

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Izberite **Dodaj podatke** in izberite vrsto dejavnosti v stranskem podoknu, ki vsebuje zahtevane podatke o transakcijah ali zgodovini nakupov.

1. Spodaj **Izberite dejavnosti**, izberite določene dejavnosti iz izbrane vrste dejavnosti, na katero želite, da se osredotoči izračun.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Stransko podokno prikazuje izbiro določenih dejavnosti pod semantično vrsto.":::

   Če dejavnosti še niste preslikali v semantično vrsto, izberite **Uredi**, da to storite. Odpre se vodena izkušnja za preslikavo semantičnih dejavnosti. Podatke preslikajte v ustrezna polja izbrane vrste dejavnosti.

1. Preslikajte semantične atribute v polja, ki so potrebna za zagon modela. Če spodnja polja niso izpolnjena, konfigurirajte razmerje med entiteto zgodovine nakupov in entiteto *Stranka*. Izberite **Shrani**.

1. V **Dodajte zahtevane podatke** korak, izberite **Naslednji** za nadaljevanje, če ne želite dodati več dejavnosti.


# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Dodajanje dodatnih podatkov (izbirno)

Konfigurirajte odnos med entiteto dejavnosti kupca in entiteto *stranke*.

1. Izberite polje, ki prepozna stranko v tabeli dejavnosti strank. Lahko je neposredno povezano s primarnim ID-jem stranke za vašo entiteto *stranke*.

1. Izberite entiteto, ki je vaša primarna entiteta *Stranka*.

1. Vnesite ime, ki opisuje odnos.

#### <a name="customer-activities"></a>Dejavnosti stranke

1. Po želji izberite **Dodaj podatke** za **Dejavnosti strank**.

1. Izberite vrsto semantične dejavnosti, ki vsebuje podatke, ki jih želite uporabiti, nato izberite eno ali več dejavnosti v razdelku **Dejavnosti**.

1. Izberite vrsto dejavnosti, ki se ujema z vrsto dejavnosti stranke, ki jo konfigurirate. Izberite **Ustvari novo** in izberite razpoložljivo vrsto dejavnosti ali ustvarite novo vrsto.

1. Izberite **Naprej**, nato **Shrani**.

1. Če imate še kakšno dejavnost strank, ki bi jo radi vključili, ponovite zgornje korake.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

### <a name="select-prediction-level"></a>Izbira ravni predvidevanja

Večina predvidevanj je ustvarjenih na ravni strank. V nekaterih primerih to morda ni dovolj natančno, da bi zadostilo vašim poslovnim potrebam. S to funkcijo lahko na primer napoveste izgubo za vejo stranke in ne za stranko kot celoto.

1. Če želite ustvariti predvidevanje na bolj razdrobljeni ravni kot stranka, izberite **Izberite entiteto za sekundarno raven**. Če možnost ni na voljo, preverite, ali ste dokončali prejšnji razdelek.

1. Razširite entitete, med katerimi želite izbrati sekundarno raven, ali uporabite polje filtra za iskanje za filtriranje izbranih možnosti.

1. Izberite atribut, ki ga želite uporabiti kot sekundarno raven, nato izberite **Dodaj**.

1. Izberite **Naprej**.

> [!NOTE]
> Entitete, ki so na voljo v tem razdelku, so prikazane, ker imajo odnos z entiteto, ki ste jo izbrali v prejšnjem razdelku. Če ne vidite entitete, ki jo želite dodati, se prepričajte, da ima veljaven odnos v **Odnosi**. Za to konfiguracijo sta veljavna samo odnosa ena proti ena in mnogo proti ena.

### <a name="add-additional-data-optional"></a>Dodajanje dodatnih podatkov (izbirno)

Konfigurirajte odnos med entiteto dejavnosti kupca in entiteto *stranke*.

1. Izberite polje, ki prepozna stranko v tabeli dejavnosti strank. Lahko je neposredno povezano s primarnim ID-jem stranke za vašo entiteto *stranke*.

1. Izberite entiteto, ki je vaša primarna entiteta *Stranka*.

1. Vnesite ime, ki opisuje odnos.

#### <a name="customer-activities"></a>Dejavnosti stranke

1. Po želji izberite **Dodaj podatke** za **Dejavnosti strank**.

1. Izberite vrsto semantične dejavnosti, ki vsebuje podatke, ki jih želite uporabiti, nato izberite eno ali več dejavnosti v razdelku **Dejavnosti**.

1. Izberite vrsto dejavnosti, ki se ujema z vrsto dejavnosti stranke, ki jo konfigurirate. Izberite **Ustvari novo** in izberite razpoložljivo vrsto dejavnosti ali ustvarite novo vrsto.

1. Izberite **Naprej**, nato **Shrani**.

1. Če imate še kakšno dejavnost strank, ki bi jo radi vključili, ponovite zgornje korake.

#### <a name="customers-data"></a>Podatki o strankah

1. Po želji izberite **Dodaj podatke** za **Podatki o strankah**.

1. Preslikajte semantične atribute v polja v vaših podatkih o strankah kot prepoznana. Podatki v uporabljenih poljih se ne bi smeli pogosto spreminjati, da bi zagotovili najboljšo zmogljivost modela. Na primer, pri izbiri polja za »Razvrstitev«, ki se spreminja vsak mesec, bi bila uporabljena le zadnja vrednost v predvidevanju, čeprav v preteklosti ista vrednost morda ne bi veljala za stranko pri izdelavi vzorcev predvidevanja.

1. Izberite **Naprej**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Navajanje izbirnega seznama referenčnih računov

Dodajte seznam poslovnih strank in računov, ki jih želite uporabiti kot referenčne vrednosti. Dobili boste [podrobnosti o teh referenčnih računih](#review-a-prediction-status-and-results), vključno z njihovo oceno o izgubi in najvplivnejšimi funkcijami, ki so vplivale na njihovo predvidevanje izgub.

1. Izberite **+ Dodaj stranke**.

1. Izberite stranke, ki delujejo kot referenčna vrednost.

1. Če želite nadaljevati, izberite **Naprej**.

---

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
     Vse stranke niso nujno tudi dejavne stranke. Nekatere od njih morda že dolgo niso bile dejavne in se na podlagi definicije izgube že štejejo za izgubljene. Predvidevanje tveganja za izgubo za stranke, ki so že izgubile, ni koristno, ker niso občinstvo, ki nas zanima.
   - **Predvideno polje**: to polje je zapolnjeno samo za nekatere vrste predvidevanj in se ne uporablja pri predvidevanju izgub.
   - **Stanje:** stanje izvajanja predvidevanja.
        - **V čakalni vrsti**: predvidevanje čaka, da se zaženejo drugi postopki.
        - **Osveževanje**: predvidevanje se trenutno izvaja za ustvarjanje rezultatov, ki bodo stekli v izhodno entiteto.
        - **Ni uspelo:** izvajanje predvidevanja ni uspelo. [Preglejte dnevniške datoteke](manage-predictions.md#troubleshoot-a-failed-prediction) za več podrobnosti.
        - **Uspelo:** predvidevanje je uspelo. Izberite **Pogled** pod navpičnimi tremi pikami za pregled predvidevanja
   - **Urejeno**: datum, ko je bila spremenjena konfiguracija predvidevanja.
   - **Nazadnje osveženo**: datum, ko je predvidevanje osvežilo rezultate v izhodni entiteti.

1. Izberite navpične tri pike poleg predvidevanja, za katerega želite pregledati rezultate, in izberite **Pogled**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Oglejte si kontrolnik, da vidite rezultate predvidevanja.":::

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

1. Na strani z rezultati so trije primarni razdelki podatkov:
   - **Učinkovitost modela za kvalifikacijo**: A, B ali C so možni rezultati. Ta rezultat kaže na učinkovitost predvidevanja in vam lahko pomaga pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti. Rezultati se določijo na podlagi naslednjih pravil: 
        - **A**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, večji od izhodiščne stopnje za vsaj 10 %.
            
        - **B**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, do 10 % večji od izhodiščne stopnje.
            
        - **C**, ko je model natančno napovedal manj kot 50 % vseh predvidevanj ali ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, manjši od izhodiščne stopnje.
               
        - **Izhodišče** uporabi vnos časovnega obdobja predvidevanja za model (na primer eno leto) in model ustvari različne delce časa tako, da ga deli z 2, dokler ne doseže enega meseca ali manj. Te delce uporablja za ustvarjanje poslovnega pravila za stranke, ki niso opravile nakupa v tem časovnem okviru. Te stranke se štejejo za izgubljene. Kot izhodiščni model je izbrano časovno pravilo poslovanja z najvišjo zmožnostjo predvidevanja, kdo se bo verjetno izgubil.
            
    - **Verjetnost izgube (število strank)**: skupine strank na podlagi predvidenega tveganja za izgubo. Ti podatki vam bodo lahko pozneje v pomoč, če boste želeli ustvariti segment strank z visokim tveganjem za izgubo. Takšni segmenti vam pomagajo razumeti, kako mora biti nastavljena vaša prekinitev za članstvo v segmentu.
       
    - **Najvplivnejši dejavniki**: ob ustvarjanju predvidevanja se upošteva veliko dejavnikov. Vsak od dejavnikov ima svoj pomen, izračunan za združena predvidevanja, ki jih ustvari model. S temi dejavniki lahko preverite veljavnost rezultatov predvidevanja ali pa te podatke uporabite pozneje, da [ustvarite segmente](segments.md), kar bi lahko vplivalo na tveganje izgube za stranke.


# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

1. Na strani z rezultati so trije primarni razdelki podatkov:
   - **Učinkovitost modela za kvalifikacijo**: A, B ali C so možni rezultati. Ta rezultat kaže na učinkovitost predvidevanja in vam lahko pomaga pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti. Rezultati se določijo na podlagi naslednjih pravil: 
        - **A**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, večji od izhodiščne stopnje za vsaj 10 %.
            
        - **B**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, do 10 % večji od izhodiščne stopnje.
            
        - **C**, ko je model natančno napovedal manj kot 50 % vseh predvidevanj ali ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, manjši od izhodiščne stopnje.
               
        - **Izhodišče** uporabi vnos časovnega obdobja predvidevanja za model (na primer eno leto) in model ustvari različne delce časa tako, da ga deli z 2, dokler ne doseže enega meseca ali manj. Te delce uporablja za ustvarjanje poslovnega pravila za stranke, ki niso opravile nakupa v tem časovnem okviru. Te stranke se štejejo za izgubljene. Kot izhodiščni model je izbrano časovno pravilo poslovanja z najvišjo zmožnostjo predvidevanja, kdo se bo verjetno izgubil.
            
    - **Verjetnost izgube (število strank)**: skupine strank na podlagi predvidenega tveganja za izgubo. Ti podatki vam bodo lahko pozneje v pomoč, če boste želeli ustvariti segment strank z visokim tveganjem za izgubo. Takšni segmenti vam pomagajo razumeti, kako mora biti nastavljena vaša prekinitev za članstvo v segmentu.
       
    - **Najvplivnejši dejavniki**: ob ustvarjanju predvidevanja se upošteva veliko dejavnikov. Vsak od dejavnikov ima svoj pomen, izračunan za združena predvidevanja, ki jih ustvari model. S temi dejavniki lahko preverite veljavnost rezultatov predvidevanja ali pa te podatke uporabite pozneje, da [ustvarite segmente](segments.md), kar bi lahko vplivalo na tveganje izgube za stranke.


1. Za poslovne račune boste našli stran z informacijami **Analiza vplivnih funkcij**. Vsebuje štiri razdelke podatkov:

    - Element, izbran v desnem podoknu, določa vsebino te strani. Izberite element v razdelku **Najboljše stranke** ali **Stranke z referenčno vrednostjo**. Oba seznama sta razvrščena po padajoči vrednosti ocene izgube, ne glede na to, ali je ocena samo za stranko ali kombinirana ocena za stranke in kategorijo izdelkov sekundarne ravni.
        
        - **Najboljše stranke**: seznam 10 strank z največjim tveganjem izgube in najnižjim tveganjem izgube na podlagi njihovih ocen izgube. 
        - **Stranke z referenčno vrednostjo**: seznam do 10 strank, ki so bile izbrane med konfiguracijo modela.
 
    - **Ocena izgube:** v desnem podoknu prikaže oceno izgube izbranega elementa.
    
    - **Porazdelitev tveganja za izgubo:** prikazuje porazdelitev tveganja za izgubo med strankami in percentil, v katerem je izbrana stranka. 
    
    - **Najpogostejše funkcije, ki povečujejo in zmanjšujejo tveganje za izgubo:** za izbran element v desnem podoknu je naštetih pet najpogostejših funkcij, ki so povečale in zmanjšale tveganje za izgubo. Za vsako vplivno funkcijo najdete vrednost funkcije za ta element in njen vpliv na oceno izgube. Prikazana je tudi povprečna vrednost vsake funkcije v segmentih strank z nizko, srednjo in visoko stopnjo izgube. Pomaga bolje kontekstualizirati vrednosti najboljših vplivnih lastnosti izbranega elementa in jih primerjati z nizko, srednjo in visoko stopnjo izgube v segmentih strank.

       - Nizka: računi ali kombinacije računa in sekundarne ravni z oceno izgube med 0 in 0,33
       - Srednja: računi ali kombinacije računov in sekundarnih ravni z oceno izgube med 0,33 in 0,66
       - Visoka: računi ali kombinacije računov in sekundarnih ravni z oceno izgube, ki je večja od 0,66
    
       Ko predvidevate izgubo na ravni računa, se pri izpeljavi povprečnih vrednosti funkcij za segmente izgub upoštevajo vsi računi. Za predvidevanja izgube na sekundarni ravni za vsak račun je izpeljava segmentov izgub odvisna od sekundarne ravni elementa, izbranega v stranskem podoknu. Na primer, če ima element sekundarno raven kategorije izdelka = pisarniški material, se pri določanju povprečnih vrednosti funkcij za segmente izgub upoštevajo le elementi, ki imajo kot kategorijo izdelkov pisarniški material. Ta logika se uporablja za zagotovitev zadovoljive primerjave vrednosti funkcij elementa s povprečnimi vrednostmi v segmentih z nizko, srednjo in visoko stopnjo izgube.

       V nekaterih primerih je povprečna vrednost segmentov nizke, srednje ali visoke stopnje izgube prazna ali ni na voljo, ker na podlagi zgornje definicije ni elementov, ki bi pripadali ustreznim segmentom izgub.
       
       > [!NOTE]
       > Razlaga vrednosti pod povprečnimi nizkimi, srednjimi in visokimi stolpci je različna za kategorijske značilnosti, kot sta država ali panoga. Ker se pojem »povprečne« vrednosti funkcije ne uporablja za kategorijske značilnosti, so vrednosti v teh stolpcih delež strank v segmentih z nizko, srednjo in visoko stopnjo izgube, ki imajo enako vrednost kategorijskega elementa v primerjavi z izdelkom, izbranim na stranski plošči.

---

## <a name="manage-predictions"></a>Upravljanje predvidevanj

Predvidevanja je mogoče optimizirati, zanje odpraviti napake, osvežiti ali izbrisati. Preglejte poročilo o uporabnosti vhodnih podatkov, če želite izvedeti, kako narediti predvidevanje hitrejše in zanesljivejše. Za več informacij odprite [Upravljanje predvidevanj](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
