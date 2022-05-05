---
title: Predvidevanje življenjske vrednosti stranke (CLV)
description: Predvidevajte prihodnje potencialne prihodke za aktivne stranke.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: 3e1b1ce00eeda1cead9ba05beae65b6903d0b9cf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643821"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Predvidevanje življenjske vrednosti stranke (CLV)

Predvidite potencialno vrednost (prihodek), ki jo bodo posamezne aktivne stranke prispevale vašemu podjetju v določenem prihodnjem časovnem obdobju. Ta funkcija vam lahko pomaga doseči različne cilje: 
- prepoznati stranke z visoko vrednostjo in obdelavo tega vpogleda,
- ustvariti strateške segmente strank na podlagi njihove potencialne vrednosti za vodenje prilagojenih akcij s ciljno usmerjenimi prodajnimi, trženjskimi in podpornimi prizadevanji,
- usmerjati razvoj izdelkov s poudarkom na funkcijah, ki povečujejo vrednost kupca,
- optimizirati prodajno ali tržno strategijo in natančneje dodeliti proračun za doseganje strank,
- prepoznati in nagraditi stranke z visoko vrednostjo s programi zvestobe ali nagrajevanja. 

## <a name="prerequisites"></a>Zahteve

Preden začnete, razmislite, kaj življenjska vrednost strank pomeni za vaše podjetje. Trenutno podpiramo predvidevanje življenjske vrednosti strank na podlagi transakcij. Predvidena vrednost stranke temelji na zgodovini poslovnih transakcij. Če želite ustvariti predvidevanje, potrebujete vsaj dovoljenja za [ sodelujočega](permissions.md).

Ker konfiguracija in zagon modela CLV ne traja veliko časa, razmislite o ustvarjanju več modelov z različnimi vhodnimi nastavitvami ter primerjajte rezultate modelov, da ugotovite, kateri primer modela najbolje ustreza vašim poslovnim potrebam.

###  <a name="data-requirements"></a>Zahteve za podatke

Potrebni so naslednji podatki, če so označeni kot neobvezni, pa so priporočljivi za večjo zmogljivost modela. Več podatkov ko model lahko obdela, bolj natančno bo predvidevanje. Zato vam priporočamo, da vključite več podatkov o dejavnostih strank, če so ti na voljo.

- Identifikator stranke: enolični identifikator, ki ustreza transakcijam posamezni stranki

- Zgodovina transakcij: dnevnik zgodovine transakcij s spodnjo semantično podatkovno shemo
    - **ID transakcije**: enolični identifikator vsake transakcije
    - **Datum transakcije**: datum, po možnosti časovni žig vsake transakcije
    - **Transakcijski znesek**: denarna vrednost (na primer prihodek ali stopnja dobička) vsake transakcije
    - **Oznaka, dodeljena vračilom** (neobvezno): logična vrednost, ki označuje, ali je transakcija vračilo 
    - **ID izdelka** (neobvezno): ID izdelka, vključenega v transakcijo

- Dodatni podatki (izbirno), na primer
    - Spletne dejavnosti: zgodovina obiska spletnega mesta, zgodovina e-pošte
    - Dejavnosti zvestobe: razmejitev nagradnih točk za zvestobo in zgodovina unovčenja
    - Dnevnik storitev za stranke , servisni klic, pritožba ali zgodovina vračila
- Podatki o dejavnostih strank (neobvezno):
    - Identifikatorji dejavnosti za razlikovanje med dejavnostmi iste vrste
    - Identifikatorji strank za preslikavo dejavnosti v stranke
    - Podatki o dejavnosti, ki vsebujejo ime in datum dejavnosti
    - Semantična podatkovna shema za dejavnosti vključuje: 
        - **Primarni ključ**: enolični identifikator dejavnosti
        - **Časovni žig**: datum in ura dogodka, ki ga je prepoznal primarni ključ
        - **Dogodek (ime aktivnosti)**: ime dogodka, ki ga želite uporabiti
        - **Podrobnosti (znesek ali vrednost)**: podrobnosti o dejavnosti stranke

- Predlagane lastnosti podatkov:
    - Zadostni zgodovinski podatki: vsaj eno leto transakcijskih podatkov. Po možnosti dve do tri leta transakcijskih podatkov za predvidevanje življenjske vrednostni strank za eno leto.
    - Več nakupov na stranko: v idealnem primeru vsaj dve do tri transakcije na ID stranke, po možnosti na več datumov.
    - Število strank: vsaj 100 enoličnih strank, po možnosti več kot 10.000 strank. Model bo propadel z manj kot 100 strankami in nezadostnimi zgodovinskimi podatki
    - Popolnost podatkov: manj kot 20 % manjkajočih vrednosti v obveznih poljih vhodnih podatkov   

> [!NOTE]
> - Model potrebuje zgodovino transakcij vaših strank. Trenutno je mogoče konfigurirati samo eno entiteto zgodovine transakcij. Če obstaja več subjektov za nakup/transakcijo, jih lahko združite Power Query pred zaužitjem podatkov.
> - Za dodatne podatke o dejavnostih strank (neobvezno) pa lahko dodate toliko entitet dejavnosti strank, kolikor želite, da jih model upošteva.

## <a name="create-a-customer-lifetime-value-prediction"></a>Ustvarjanje predvidevanja življenjske vrednosti stranke

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Izberite ploščico **Življenjska vrednost kupca** in izberite možnost **Uporabi model**. 

1. V **Življenjska vrednost stranke** podokno, izberite **Začeti**.

1. **Poimenujte ta model** in **izhodno ime entitete**, da jih ločite od drugih modelov ali entitet.

1. Izberite **Naprej**.

### <a name="define-model-preferences"></a>Opredelitev nastavitev modela

1. Nastavite **časovno obdobje predvidevanja** da določite, kako daleč v prihodnost želite napovedati življenjsko vrednost stranke.    
   Privzeto je enota nastavljena na mesece. Spremenite jo lahko v leta, da pogledate dlje v prihodnost.

   > [!TIP]
   > Če želite natančno napovedati življenjsko vrednost stranke za nastavljeno časovno obdobje, potrebujete zgodovinske podatke o primerljivem obdobju. Če želite na primer ustvariti predvidevanje življenjske vrednostni strank za naslednjih 12 mesecev, je priporočljivo, da imate vsaj 18–24 mesecev zgodovinskih podatkov.

1. Navedite, kaj **aktivne stranke** pomenijo v vašem podjetju. Nastavite časovni okvir, v katerem mora imeti stranka vsaj eno transakcijo, da se šteje za aktivno stranko. Model bo življenjsko vrednost stranke napovedal samo za aktivne stranke. 
   - **Naj model izračuna interval nakupa (priporočljivo)**: model analizira podatke in določi časovno obdobje na podlagi preteklih nakupov.
   - **Interval nastavite ročno** : če imate določeno poslovno definicijo aktivne stranke, izberite to možnost in ustrezno nastavite časovno obdobje.

1. Določite percentil **stranke visoke vrednosti**, da modelu omogočite zagotavljanje rezultatov, ki ustrezajo vaši poslovni definiciji.
    - **Izračun modela (priporočeno)**: model analizira podatke in na podlagi zgodovine transakcij vaših strank določi, kakšna je stranka z visoko vrednostjo za vaše podjetje. Model uporablja hevristično pravilo (na podlagi pravila 80/20 ali Paretovega načela) za iskanje deleža strank z visoko vrednostjo. Delež strank, ki so v preteklem obdobju ustvarile 80-odstotni kumulativni prihodek za vaše podjetje, se šteje za stranke z visoko vrednostjo. Običajno manj kot 30–40 % kupcev prispeva k 80 % skupnega prihodka. Vendar se ta številka lahko razlikuje glede na vaše podjetje in panogo.    
    - **Delež najbolj aktivnih strank**: določite stranke z visoko vrednostjo za svoje podjetje kot percentil najbolj aktivnih strank, ki porabljajo denar. S to možnostjo lahko na primer stranke z visoko vrednostjo opredelite kot 20 % najboljših strank, ki bodo v prihodnosti porabile denar.

    Če vaše podjetje stranke z visoko vrednostjo opredeljuje na drugačen način, [nam to sporočite](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Za pomik na naslednji korak izberite možnost **Naprej**.

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Pri koraku **obveznih podatkov** izberite možnost **Dodaj podatke** za **zgodovino transakcij stranke** in izberite entiteto, ki zagotavlja podatke o zgodovini transakcij/nakupov, kot je opisano v [zahtevah](#prerequisites).

1. Preslikajte semantična polja v atribute v entiteti vaše zgodovine nakupov in izberite **Naprej**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Slika konfiguracijskega koraka za preslikavo atributov podatkov za zahtevane podatke.":::
 
1. Če spodnja polja niso izpolnjena, konfigurirajte odnos iz entitete zgodovine nakupov z entiteto *stranke* in izberite možnost **Shrani**.
    1. Izberite entiteto zgodovine transakcij.
    1. Izberite polje, ki prepozna stranko v entiteti zgodovine nakupov. Povezovati se mora s primarnim ID-jem stranke vaše entitete stranke.
    1. Izberite entiteto, ki se ujema z entiteto primarne stranke.
    1. Vnesite ime, ki opisuje odnos.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Slika koraka konfiguracije za določitev odnosa z entiteto stranke.":::

1. Izberite **Naprej**.

### <a name="add-optional-data"></a>Dodajanje izbirnih podatkov

Podatki, ki odražajo interakcije ključnih strank (na primer dnevnike za splet, storitve za stranke in dogodke), dodajo kontekst zapisom transakcij. Dodatni vzorci, ki jih najdete v podatkih o dejavnostih vaših strank, lahko izboljšajo natančnost predvidevanja. 

1. Pri koraku **Dodatni podatki (neobvezno)** izberite možnost **Dodaj podatke**. Izberite entiteto dejavnosti strank, ki zagotavlja podatke o dejavnosti strank, kot je opisano v [zahtevah](#prerequisites).

1. Preslikajte semantična polja v atribute v entiteti dejavnosti strank in izberite **Naprej**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Slika konfiguracijskega koraka za preslikavo polj za dodatne podatke.":::

1. Izberite vrsto dejavnosti, ki se ujema z vrsto dejavnosti stranke, ki jo dodajate. Izberite med obstoječimi vrstami dejavnosti ali dodajte novo vrsto dejavnosti.

1. Konfigurirajte odnos med entiteto dejavnosti kupca in entiteto *stranke*.
    
    1. Izberite polje, ki prepozna stranko v tabeli dejavnosti strank. Lahko je neposredno povezano s primarnim ID-jem stranke za vašo entiteto *stranke*.
    1. Izberite entiteto *stranke*, ki se ujema z vašo primarno entiteto *stranke*.
    1. Vnesite ime, ki opisuje odnos.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Slika koraka v konfiguracijskem toku za dodajanje dodatnih podatkov in konfiguriranje dejavnosti z izpolnjenimi primeri.":::

1. Izberite **Shrani**.    
    Dodajte več podatkov, če želite vključiti še druge dejavnosti strank.

1. Izberite **Naprej**.

### <a name="set-update-schedule"></a>Nastavitev urnika posodobitev

1. Pri koraku **Urnik posodobitev podatkov** izberite pogostost za prekvalificiranje modela na podlagi najnovejših podatkov. Ta nastavitev je pomembna za posodabljanje natančnosti napovedi, ko se novi podatki vnesejo v Customer Insights. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

### <a name="review-and-run-the-model-configuration"></a>Pregled in zagon konfiguracije modela

1. Pri koraku **Pregled podrobnosti o modelu** preverite veljavnost konfiguracije predvidevanja. Na kateri koli del konfiguracije predvidevanja se lahko vrnete tako, da izberete možnost **Uredi** pod prikazano vrednostjo. Korak konfiguracije lahko izberete tudi s kazalnika napredka.

1. Če so vse vrednosti pravilno konfigurirane, izberite možnost **Shrani in zaženi**, da se model začne izvajati. Na zavihku **Moja predvidevanja** lahko vidite stanje postopka predvidevanja. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

## <a name="review-prediction-status-and-results"></a>Pregled stanja in rezultatov predvidevanja

### <a name="review-prediction-status"></a>Pregled stanja predvidevanja

1.  Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.
2.  Izberite predvidevanje, ki ga želite pregledati.

- **Ime predvidevanja:** ime predvidevanja, navedeno ob ustvarjanju.
- **Vrsta predvidevanja:** vrsta modela, uporabljena za predvidevanje
- **Izhodna entiteta:** ime entitete za shranjevanje rezultatov predvidevanja. V razdelku **Podatki** > **Entitete** najdite entiteto s tem imenom.
- **Predvideno polje:** to polje je zapolnjeno samo za nekatere vrste predvidevanj in se ne uporablja pri predvidevanju življenjske vrednosti stranke.
- **Stanje:** stanje izvajanja predvidevanja.
    - **V čakalni vrsti:** predvidevanje čaka, da se zaključijo drugi postopki.
    - **Osveževanje:** predvidevanje se trenutno izvaja za ustvarjanje rezultatov, ki bodo združeni v izhodni entiteti.
    - **Ni uspelo:** izvajanje predvidevanja ni uspelo. [Preglejte dnevniške datoteke](manage-predictions.md#troubleshoot-a-failed-prediction) za več podrobnosti.
    - **Uspelo:** predvidevanje je uspelo. Pod navpičnimi tremi pikami izberite možnost **Pogled** za pregled rezultatov predvidevanja.
- **Urejeno**: datum, ko je bila spremenjena konfiguracija predvidevanja.
- **Nazadnje osveženo**: datum, ko je predvidevanje osvežilo rezultate v izhodni entiteti.

### <a name="review-prediction-results"></a>Pregled rezultatov predvidevanja

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite predvidevanje, za katerega želite pregledati rezultate.

Na strani z rezultati so trije primarni razdelki podatkov.

- **Uspešnost modela usposabljanja** : A, B ali C so možne ocene. Ta ocena označuje uspešnost predvidevanja in vam lahko pomaga pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti. Izberite možnost **Več o tem rezultatu** za boljše razumevanje osnovnih meritev uspešnosti modela in kako je pridobljena končna ocena uspešnosti modela.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Slika polja s podatki o oceni modela z oceno A":::

  Na podlagi definicije strank z visoko vrednostjo, ki je bila podana med konfiguriranjem predvidevanja, sistem oceni, kako je model umetne inteligence deloval pri napovedovanju strank z visoko vrednostjo v primerjavi z osnovnim modelom.    

  Ocene so določene na podlagi naslednjih pravil:
  - **A**, če model natančno napove vsaj 5 % več kupcev z visoko vrednostjo v primerjavi z osnovnim modelom.
  - **B**, če model natančno napove 0–5 % več kupcev z visoko vrednostjo v primerjavi z osnovnim modelom.
  - **C**, če model natančno napove manj kupcev z visoko vrednostjo v primerjavi z osnovnim modelom.

  Podokno **Ocena modela** prikazuje nadaljnje podrobnosti o zmogljivosti modela umetne inteligence in osnovnega modela. Osnovni model uporablja pristop, ki ne temelji na umetni inteligenci, za izračun življenjske vrednosti strank, ki temelji predvsem na preteklih nakupih, ki jih opravijo stranke.     
  Standardna formula, ki se uporablja za izračun življenjske vrednosti strank v osnovnem modelu:    

  _**Življenjska vrednost stranke za posamezno stranko** = povprečni znesek mesečnega nakupa, ki ga stranka opravi v oknu dejavnih strank * število mesecev v obdobju predvidevanja življenjske vrednostni strank * splošna stopnja ohranitve vseh strank_

  Model umetne inteligence se primerja z osnovnim modelom na podlagi dveh meritev uspešnosti modela.
  
  - **Uspešnost pri predvidevanju strank z visoko vrednostjo**

    Oglejte si razliko pri napovedovanju kupcev z visoko vrednostjo z uporabo modela umetne inteligence v primerjavi z osnovnim modelom. 84-odstotna stopnja uspešnosti na primer pomeni, da je od vseh strank z visoko vrednostjo v podatkih za usposabljanje model umetne inteligence lahko natančno zajel 84 % strank. Nato to stopnjo uspešnosti primerjamo s stopnjo uspešnosti osnovnega modela, da poročamo o relativni spremembi. Ta vrednost se uporablja za dodelitev ocene modelu.

  - **Metrika napak**
    
    Druga meritev omogoča pregled splošne uspešnosti modela z vidika napak pri predvidevanju prihodnjih vrednosti. Za oceno te napake uporabljamo meritev korena povprečne kvadratne napake (RMSE). Meritev RMSE je standardni način merjenja napak modela pri predvidevanju kvantitativnih podatkov. Meritev RMSE modela umetne inteligence se primerja z meritvijo RMSE osnovnega modela, poročana pa je relativna razlika.

  Model umetne inteligence daje prednost natančnemu razvrščanju strank glede na vrednost, ki jo prinašajo podjetju. Tako se za pridobitev končne ocene modela uporablja le stopnja uspešnosti predvidevanja strank z visoko vrednostjo. Meritev RMSE je občutljiva na odstopanja. V primerih, ko imate majhen delež strank z izjemno visokimi vrednostmi nakupa, splošna meritev RMSE morda ne zagotovi celotne slike o uspešnosti modela.   

- **Vrednost strank po percentilu**: z uporabo vaše definicije strank z visoko vrednostjo so stranke na podlagi predvidevane življenjske vrednosti stranke razvrščene v skupine z nizko in visoko vrednostjo ter prikazane v grafikonu. Če kazalec miške premaknete nad stolpce v histogramu, lahko vidite število strank v vsaki skupini in povprečno življenjsko vrednost stranke te skupine. Ti podatki lahko pomagajo, če želite [ustvariti segmente kupcev](segments.md) na podlagi predvidevanja življenjske vrednosti stranke.

- **Najvplivnejši dejavniki** : pri ustvarjanju predvidevanja življenjske vrednosti stranke upoštevamo različne dejavnike na podlagi vhodnih podatkov, posredovanih modelu umetne inteligence. Za vsakega od dejavnikov je izračunan pomen za združena predvidevanja, ki jih ustvari model. Te dejavnike lahko uporabite za pomoč pri preverjanju rezultatov predvidevanja. Ti dejavniki omogočajo tudi večji vpogled v najvplivnejše dejavnike, ki so prispevali k predvidevanju življenjske vrednosti stranke za vse vaše stranke.

## <a name="manage-predictions"></a>Upravljanje predvidevanj

Predvidevanja je mogoče optimizirati, zanje odpraviti napake, osvežiti ali izbrisati. Preglejte poročilo o uporabnosti vhodnih podatkov, če želite izvedeti, kako narediti predvidevanje hitrejše in zanesljivejše. Za več informacij glejte razdelek [Upravljanje predvidevanj](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
