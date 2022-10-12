---
title: Predvidevanje skupne vrednosti stranke (CLV)
description: Predvidevajte prihodnje potencialne prihodke za aktivne stranke.
ms.date: 09/30/2022
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
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610394"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predvidevanje skupne vrednosti stranke (CLV)

Predvidite potencialno vrednost (prihodek), ki jo bodo posamezne aktivne stranke prispevale vašemu podjetju v določenem prihodnjem časovnem obdobju. Ta predvidevanje vam pomaga:

- Prepoznajte stranke z visoko vrednostjo in obdelajte ta vpogled.
- Ustvarite strateške segmente strank na podlagi njihove potencialne vrednosti za vodenje prilagojenih kampanj s ciljno usmerjeno prodajo, trženjem in podporo.
- Vodite razvoj izdelka z osredotočanjem na funkcije, ki povečujejo vrednost za stranke.
- Optimizirajte prodajno ali tržno strategijo in natančneje dodelite proračun za doseganje strank.
- Prepoznajte in nagradite stranke z visoko vrednostjo prek programov zvestobe ali nagrajevanja.

Ugotovite, kaj CLV pomeni za vaše podjetje. Podpiramo CLV, ki temelji na transakcijah predvidevanje. Predvidena vrednost stranke temelji na zgodovini poslovnih transakcij. Razmislite o ustvarjanju več modelov z različnimi preferencami vnosa in primerjajte rezultate modelov, da vidite, kateri scenarij modela najbolje ustreza vašim poslovnim potrebam.

> [!TIP]
> Preizkusite CLV predvidevanje z uporabo vzorčnih podatkov: [Doživljenjska vrednost stranke (CLV) predvidevanje vzorčni vodnik](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [sodelavec](permissions.md) dovoljenja
- Vsaj 100 edinstvenih strank, po možnosti več kot 10.000 strank
- Identifikator stranke, enolični identifikator za povezovanje transakcij s posamezno stranko
- Vsaj eno leto zgodovine transakcij, po možnosti dve do tri leta. V idealnem primeru vsaj dve do tri transakcije na ID stranke, po možnosti na več datumov. Zgodovina transakcij mora vsebovati:
  - **ID transakcije**: enolični identifikator vsake transakcije
  - **Datum transakcije** : Datum ali časovni žig vsake transakcije
  - **Transakcijski znesek**: denarna vrednost (na primer prihodek ali stopnja dobička) vsake transakcije
  - **Oznaka, dodeljena vračilom** : Logična vrednost true/false, ki označuje, ali je transakcija vračilo
  - **ID izdelka** : ID izdelka, vključenega v transakcijo
- Podatki o dejavnostih strank:
  - **Primarni ključ** : Enolični identifikator za dejavnost
  - **Časovni žig** : Datum in čas dogodka, ki ga identificira primarni ključ
  - **Dogodek (ime dejavnosti)** : ime dogodka, ki ga želite uporabiti
  - **Podrobnosti (znesek ali vrednost)**: podrobnosti o dejavnosti stranke
- Dodatni podatki, kot so:
  - Spletne dejavnosti: zgodovina obiskov spletne strani ali zgodovina e-pošte
  - Dejavnosti zvestobe: zgodovina zbiranja in unovčenja nagradnih točk zvestobe
  - Dnevnik storitve za stranke: zgodovina klicev servisa, pritožb ali vračil
  - Informacije o profilu stranke
- Manj kot 20 % manjkajočih vrednosti v obveznih poljih

> [!NOTE]
> Konfigurirati je mogoče samo eno entiteto zgodovine transakcij. Če obstaja več subjektov nakupa ali transakcije, jih združite Power Query pred vnosom podatkov.

## <a name="create-a-customer-lifetime-value-prediction"></a>Ustvarjanje predvidevanja življenjske vrednosti stranke

Izberite **Shrani osnutek** kadar koli shranite predvidevanje kot osnutek. Osnutek predvidevanje se prikaže v **Moje napovedi** zavihek.

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Življenjska vrednost stranke** ploščica.

1. Izberite **Začetek**.

1. **Poimenujte ta model** in **izhodno ime entitete**, da jih ločite od drugih modelov ali entitet.

1. Izberite **Naprej**.

### <a name="define-model-preferences"></a>Opredelitev nastavitev modela

1. Nastavite **časovno obdobje predvidevanja** da določite, kako daleč v prihodnost želite napovedati življenjsko vrednost stranke. Privzeto je enota nastavljena na mesece.

   > [!TIP]
   > Za natančno napoved CLV za nastavljeno časovno obdobje je potrebno primerljivo obdobje preteklih podatkov. Na primer, če želite napovedati CLV za naslednjih 12 mesecev, imejte vsaj 18–24 mesecev zgodovinskih podatkov.

1. Nastavite časovni okvir, v katerem mora imeti stranka vsaj eno transakcijo, da se šteje za aktivno stranko. Model predvideva samo CLV za **Aktivne stranke**.
   - **Naj model izračuna interval nakupa (priporočeno)** : Model analizira vaše podatke in določi časovno obdobje na podlagi preteklih nakupov.
   - **Interval nastavite ročno** : Časovno obdobje za vašo definicijo aktivne stranke.

1. Določite percentil za **Stranka visoke vrednosti**.
    - **Izračun modela (priporočeno)** : Model uporablja pravilo 80/20. Delež strank, ki so v preteklem obdobju ustvarile 80-odstotni kumulativni prihodek za vaše podjetje, se šteje za stranke z visoko vrednostjo. Običajno manj kot 30–40 % kupcev prispeva k 80 % skupnega prihodka. Vendar se ta številka lahko razlikuje glede na vaše podjetje in panogo.
    - **Odstotek najboljših aktivnih strank** : Poseben percentil za stranko z visoko vrednostjo. Na primer, enter **25** opredeliti kupce z visoko vrednostjo kot 25 % najvišjih plačljivih strank v prihodnosti.

    Če vaše podjetje stranke z visoko vrednostjo opredeljuje na drugačen način, [nam to sporočite](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Izberite **Naprej**.

### <a name="add-required-data"></a>Dodajanje zahtevanih podatkov

1. Izberite **Dodajte podatke** za **Zgodovina transakcij strank**.

1. Izberite vrsto semantične dejavnosti, **Prodajni nalog** oz **SalesOrderLine**, ki vsebuje zgodovino transakcij. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti semantično preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do semantične preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Dodajte zahtevane podatke za model CLV":::

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Dodajte več dejavnosti ali izberite **Naslednji**.

### <a name="add-optional-activity-data"></a>Dodajte neobvezne podatke o dejavnosti

Podatki, ki odražajo interakcije ključnih strank (na primer dnevnike za splet, storitve za stranke in dogodke), dodajo kontekst zapisom transakcij. Dodatni vzorci, ki jih najdete v podatkih o dejavnostih vaših strank, lahko izboljšajo natančnost predvidevanja.

1. Izberite **Dodajte podatke** Spodaj **Izboljšajte vpogled v model z dodatnimi podatki o dejavnosti**.

1. Izberite vrsto dejavnosti, ki se ujema z vrsto dejavnosti stranke, ki jo dodajate. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Izberite **Naprej**.

1. [Dodajte neobvezne podatke o strankah](#add-optional-customer-data) ali izberite **Naslednji** in pojdi na [Nastavite razpored posodabljanja](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Dodajte neobvezne podatke o strankah

Izberite med 18 pogosto uporabljenimi atributi profila strank, ki jih želite vključiti kot vhod v model. Ti atributi lahko vodijo do bolj prilagojenih, ustreznih in uporabnih rezultatov modela za primere vaše poslovne uporabe.

Na primer: Contoso Coffee želi predvideti življenjsko vrednost kupca, da cilja na stranke visoke vrednosti s prilagojeno ponudbo, povezano z lansiranjem njihovega novega aparata za espresso. Contoso uporablja model CLV in doda vseh 18 atributov profila strank, da vidi, kateri dejavniki vplivajo na njihove stranke z največjo vrednostjo. Ugotavljajo, da je lokacija stranke najvplivnejši dejavnik za te stranke.
S temi informacijami organizirajo lokalni dogodek za lansiranje aparata za espresso in sodelujejo z lokalnimi prodajalci za prilagojene ponudbe in posebno izkušnjo na dogodku. Brez teh informacij bi Contoso morda pošiljal samo splošna marketinška e-poštna sporočila in zamudil priložnost za prilagoditev za ta lokalni segment svojih strank z visoko vrednostjo.

1. Izberite **Dodajte podatke** Spodaj **Še bolj izboljšajte vpogled v model z dodatnimi podatki o strankah**.

1. Za **Entiteta**, izberite **Stranka: CustomerInsights** da izberete poenoten profil stranke, ki se preslika v podatke atributov stranke. Za **identifikacijska številka stranke**, izberite **System.Customer.CustomerId**.

1. Preslikajte več polj, če so podatki na voljo v vaših poenotenih profilih strank.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Primer preslikanih polj za podatke profila stranke.":::

1. Izberite **Shrani**.

1. Izberite **Naprej**.

### <a name="set-update-schedule"></a>Nastavitev urnika posodobitev

1. Izberite pogostost za ponovno usposabljanje vašega modela na podlagi najnovejših podatkov. Ta nastavitev je pomembna za posodobitev točnosti napovedi, ko se v Customer Insights vnesejo novi podatki. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

### <a name="review-and-run-the-model-configuration"></a>Pregled in zagon konfiguracije modela

The **Pregled in zagon** korak prikazuje povzetek konfiguracije in nudi možnost spreminjanja, preden ustvarite predvidevanje.

1. Izberite **Uredi** na katerem koli od korakov za pregled in morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Shrani in zaženi** da začnete izvajati model. Izberite **Dokončano**. The **Moje napovedi** zavihek se prikaže med ustvarjanjem predvidevanje. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Oglejte si predvidevanje rezultate

1. Pojdi do **Inteligenca** > **Napovedi**.

1. V **Moje napovedi** izberite predvidevanje, ki si ga želite ogledati.

Na strani z rezultati so trije primarni razdelki podatkov.

- **Učinkovitost modela usposabljanja** : Ocene A, B ali C označujejo uspešnost predvidevanje in vam lahko pomagajo pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Slika polja s podatki o oceni modela z oceno A":::

  Customer Insights ocenjuje, kako je model AI uspel pri napovedovanju strank z visoko vrednostjo v primerjavi z osnovnim modelom.

  Ocene so določene na podlagi naslednjih pravil:
  - **A**, če model natančno napove vsaj 5 % več kupcev z visoko vrednostjo v primerjavi z osnovnim modelom.
  - **B**, če model natančno napove 0–5 % več kupcev z visoko vrednostjo v primerjavi z osnovnim modelom.
  - **C**, če model natančno napove manj kupcev z visoko vrednostjo v primerjavi z osnovnim modelom.
  
  Izberite [**Več o tem rezultatu**](#learn-about-the-score) odpreti **Ocena modela** podokno, ki prikazuje dodatne podrobnosti o zmogljivosti modela AI in osnovnem modelu. Pomagal vam bo bolje razumeti osnovne meritve uspešnosti modela in kako je bila izpeljana končna ocena uspešnosti modela. Osnovni model uporablja pristop, ki ne temelji na umetni inteligenci, za izračun življenjske vrednosti strank, ki temelji predvsem na preteklih nakupih, ki jih opravijo stranke.

- **Vrednost strank po percentilu** : Stranke z nizko in visoko vrednostjo so prikazane v grafikonu. Premaknite miškin kazalec nad stolpce v histogramu, da vidite število strank v vsaki skupini in povprečni CLV te skupine. Po želji, [ustvarite segmente strank](prediction-based-segment.md) na podlagi njihovih napovedi CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Vrednost strank po percentilu za model CLV":::

- **Najvplivnejši dejavniki** : pri ustvarjanju predvidevanja življenjske vrednosti stranke upoštevamo različne dejavnike na podlagi vhodnih podatkov, posredovanih modelu umetne inteligence. Za vsakega od dejavnikov je izračunan pomen za združena predvidevanja, ki jih ustvari model. Uporabite te dejavnike za pomoč pri potrditvi rezultatov predvidevanje. Ti dejavniki omogočajo tudi večji vpogled v najvplivnejše dejavnike, ki so prispevali k predvidevanju življenjske vrednosti stranke za vse vaše stranke.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Najvplivnejši dejavniki za model CLV":::

### <a name="learn-about-the-score"></a>Več o rezultatu

Standardna formula, ki se uporablja za izračun življenjske vrednosti strank v osnovnem modelu:

 _**CLV za vsako stranko** = Povprečni mesečni nakup stranke v oknu za aktivne stranke * Število mesecev v obdobju CLV predvidevanje * Skupna stopnja zadrževanja vseh strank_

Model umetne inteligence se primerja z osnovnim modelom na podlagi dveh meritev uspešnosti modela.
  
- **Uspešnost pri predvidevanju strank z visoko vrednostjo**

  Oglejte si razliko pri napovedovanju kupcev z visoko vrednostjo z uporabo modela umetne inteligence v primerjavi z osnovnim modelom. 84-odstotna stopnja uspešnosti na primer pomeni, da je od vseh strank z visoko vrednostjo v podatkih za usposabljanje model umetne inteligence lahko natančno zajel 84 % strank. Nato to stopnjo uspešnosti primerjamo s stopnjo uspešnosti osnovnega modela, da poročamo o relativni spremembi. Ta vrednost se uporablja za dodelitev ocene modelu.

- **Metrika napak**

  Oglejte si splošno učinkovitost modela v smislu napake pri napovedovanju prihodnjih vrednosti. Za oceno te napake uporabljamo meritev korena povprečne kvadratne napake (RMSE). Meritev RMSE je standardni način merjenja napak modela pri predvidevanju kvantitativnih podatkov. Meritev RMSE modela umetne inteligence se primerja z meritvijo RMSE osnovnega modela, poročana pa je relativna razlika.

Model umetne inteligence daje prednost natančnemu razvrščanju strank glede na vrednost, ki jo prinašajo podjetju. Tako se za pridobitev končne ocene modela uporablja le stopnja uspešnosti predvidevanja strank z visoko vrednostjo. Meritev RMSE je občutljiva na odstopanja. V primerih, ko imate majhen delež strank z izjemno visokimi vrednostmi nakupa, splošna meritev RMSE morda ne zagotovi celotne slike o uspešnosti modela.

[!INCLUDE [footer-include](includes/footer-banner.md)]
