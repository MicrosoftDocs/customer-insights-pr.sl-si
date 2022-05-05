---
title: Analiza občutkov za povratne informacije strank
description: Naučite se uporabljati model analize razpoloženja na povratnih informacijah strank v Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e51225bbfcd445180b12661cba12256c3f042045
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643521"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizirajte razpoloženje v povratnih informacijah strank (predogled)

Kupci danes pričakujejo visoko kakovostne izdelke, storitve in izkušnje. Še posebej stranke, ki delijo svoje povratne informacije. Za organizacije je zelo zahtevno analizirati naraščajočo količino podatkov, ne da bi zmanjšali natančnost in zvišali stroške dela. Dynamics 365 Customer Insights ponuja model analize razpoloženja za povratne informacije strank, ki omogoča organizacijam, da natančneje in z nižjimi stroški analizirajo svoje podatke.

Analiza občutkov vam omogoča, da sintetizirate počutje strank in prepoznate poslovne vidike kot priložnosti za izboljšave. Ta funkcija Customer Insights vam pomaga razumeti, kaj deluje dobro in kaj morate obravnavati. Osredotočite se na najbolj pomembna in najbolj vplivna področja poslovanja, da izboljšate izkušnjo za svoje stranke. Navsezadnje vam lahko pomaga pri spodbujanju poslovnih dejanj, ki omogočajo izkušnje, ki vodijo v visoko zadovoljstvo in zvestobo strank.

## <a name="overview"></a>Pregled

Funkcija analize razpoloženja ustvari dva izpeljana vpogleda na ID stranke. Ocena razpoloženja (od -5 do 5) in seznam veljavnih poslovnih vidikov (področij poslovanja) vam skupaj pomagata bolje razumeti povratne informacije strank. 

Te informacije vam lahko pomagajo doseči naslednje rezultate: 
- Pridobite pregled nad čustvi strank do blagovne znamke ali organizacije
- Prepoznajte stranke z negativnimi čustvi, da osredotočite svoje akcije in dejavnosti ter optimizirate za višjo donosnost  
- Prepoznajte poslovne vidike s težavami, na katere so opozorile stranke  
- Segmentirajte stranke na podlagi njihovega občutka za izvajanje prilagojenih kampanj s ciljno usmerjeno prodajo, trženjem in podporo
- Optimizirajte poslovanje tako, da obravnavate vprašanja ali priložnosti, ki so jih omenile stranke
- Prepoznajte poslovne vidike, ki delajo dobro, in nagradite zadovoljne stranke s programi zvestobe in promocije

Da bi zagotovili, da lahko zaupate rezultatom modelov, nudimo pregledne informacije o tem, kako modeli sprejemajo odločitve. Dobili boste seznam besed, ki so vplivale na odločitev modelov, da komentarjem s povratnimi informacijami dodelijo določeno oceno razpoloženja ali poslovni vidik.  

Uporabljamo dva **Modeli obdelave naravnega jezika (NLP).** : Prvi vsakemu komentarju povratne informacije dodeli oceno občutka. Drugi model povezuje vsako povratno informacijo z vsemi veljavnimi poslovnimi vidiki. Modeli so usposobljeni na podlagi javnih podatkov iz virov v družbenih medijih, maloprodaji, restavracijah, potrošniških izdelkih in avtomobilski industriji.    
  
Vnaprej določeni poslovni vidiki za model, ki ga je treba povezati s povratnimi podatki, vključujejo:
-   Upravljanje računa
-   Dokončanje nakupa in plačilo
-   Podpora za stranke
-   Prevzem v trgovini
-   Dostava in pridobivanje embalaže
-   Prednaročilo
-   Cena
-   Zasebnost in varnost
-   Promocije in nagrade
-   Prevzem in garancija
-   Zamenjava z vračilom in preklic
-   Točnost izpolnjevanja
-   Kakovost spletnega mesta/aplikacije

> [!NOTE]
> Trenutno podpiramo samo analizo razpoloženja na podlagi povratnih informacij strank v angleškem jeziku. V prihodnosti bo podprtih več jezikov. Če so naložene povratne informacije v drugih jezikih, bo model še vedno vrnil rezultate. Vendar ti rezultati ne bodo točni. 

## <a name="prerequisites"></a>Zahteve

Analiza občutkov temelji na podatkih o besedilnih povratnih informacijah, ki so šli skozi [proces poenotenja podatkov](data-unification.md). To vam toplo priporočamo [konfigurirajte svoje podatkovne entitete povratnih informacij kot entitete dejavnosti semantičnega tipa](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (vrsta povratne informacije) vnaprej. 

Če želite konfigurirati model analize razpoloženja, potrebujete vsaj [sodelavec dovoljenja](permissions.md).

Customer Insights lahko obdela do 10 milijonov zapisov povratnih informacij za en sam model. Model lahko analizira povratne komentarje do 128 besed. Če je komentar daljši, analiza upošteva samo prvih 128 besed.

### <a name="data-requirements"></a>Zahteve za podatke
  
Zahtevani so naslednji atributi podatkov:
- Poenoten ID stranke (UCID) za uskladitev zapisov podatkov o besedilnih povratnih informacijah s posamezno stranko. Ta ID je rezultat [proces poenotenja podatkov](data-unification.md).
- ID povratnih informacij
- Časovni žig povratne informacije
- Besedilo povratnih informacij   

> [!TIP]
> Analiza občutkov zahteva besedilne povratne informacije vaših strank. Trenutno je mogoče konfigurirati samo eno povratno enoto. Če obstaja več subjektov za povratne informacije, jih lahko združite Power Query preden se začne vnos podatkov.

## <a name="configure-a-sentiment-analysis"></a>Konfigurirajte analizo razpoloženja 

1. V rešitvi Customer Insights pojdite na **Obveščanje** > **Predvidevanja**.

1. Na **Analiza razpoloženja strank** ploščico, izberite **Uporabite model**.

1. V **Analiza razpoloženja strank (predogled)** podokno, izberite **Začeti**.

1. V **Ime modela** korak, zagotovite a **ime** za vašo analizo. 

1. Zagotovite **Ime izhodne entitete poslovnega vidika** in **Ime izhodne entitete ocene občutka**, nato izberite **Naslednji**.

1. V **Zahtevani podatki** korak, izberite **Dodajte podatke**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Dodajte tok podatkov v model analize razpoloženja.":::

1. V **Dodajte podatke** podoknu, izberite pomensko vrsto **Povratne informacije** s seznama.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Korak konfiguracije za izbiro dejavnosti povratnih informacij za analizo razpoloženja.":::

1. Izberite dejavnosti, ki jih želite uporabiti za to analizo občutkov, nato izberite **Naslednji**.
 
1. Preslikajte atribute v vaših podatkih v atribute modela. Izberite **Shrani** da uporabite svoje izbire. 

1. Vidite stanje preslikave podatkov. Če želite nadaljevati, izberite **Naprej**. 

1. V **Preglejte podrobnosti svojega modela** korak, potrdite konfiguracijo vaše analize razpoloženja. Vrnete se lahko na kateri koli del konfiguracije predvidevanje. Izberite **Shranite in zaženite** za začetek analize. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Korak pregleda za model razpoloženja, ki prikazuje vse konfigurirane elemente.":::

1. Izberite **Končano** da zapustite izkušnjo konfiguracije. Postopek lahko traja več ur, odvisno od količine uporabljenih podatkov. 

## <a name="review-analysis-status"></a>Pregled stanja analize

1.  Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.
2.  Izberite predvidevanje, ki ga želite pregledati.
- **Ime predvidevanja:** ime predvidevanja, navedeno ob ustvarjanju.
- **predvidevanje vrsta** : Vrsta modela, uporabljenega za predvidevanje.
- **Izhodna entiteta:** ime entitete za shranjevanje rezultatov predvidevanja. V razdelku **Podatki** > **Entitete** najdite entiteto s tem imenom.
- **Predvideno polje:** to polje je zapolnjeno samo za nekatere vrste predvidevanj in se ne uporablja pri predvidevanju življenjske vrednosti stranke.
- **Stanje:** stanje izvajanja predvidevanja.
  - **V čakalni vrsti:** predvidevanje čaka, da se zaključijo drugi postopki.
  - **Osveževanje:** predvidevanje se trenutno izvaja za ustvarjanje rezultatov, ki bodo združeni v izhodni entiteti.
  - **Ni uspelo:** izvajanje predvidevanja ni uspelo. Preglejte dnevniške datoteke za več podrobnosti.
  - **Uspelo:** predvidevanje je uspelo. Pod navpičnimi tremi pikami izberite možnost Pogled za pregled rezultatov predvidevanja.
- **Urejeno**: datum, ko je bila spremenjena konfiguracija predvidevanja.
- **Nazadnje osveženo** : Datum, ko je predvidevanje osvežil rezultate v izhodni entiteti.

## <a name="manage-sentiment-analysis"></a>Upravljajte analizo razpoloženja

Napovedi lahko optimizirate, odpravite težave, osvežite ali izbrišete. Preglejte poročilo o uporabnosti vhodnih podatkov, če želite izvedeti, kako narediti predvidevanje hitrejše in zanesljivejše. Za več informacij glejte razdelek [Upravljanje predvidevanj](manage-predictions.md).

## <a name="review-analysis-results"></a>Preglejte rezultate analize
 
1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**. 
1. Izberite ime predvidevanje, za katerega želite pregledati rezultate. V tem primeru izberite analizo razpoloženja, ki jo želite pregledati. 

### <a name="summary-tab"></a>Zavihek »Povzetek«

Na strani z rezultati so štirje primarni razdelki podatkov. 

- **Povprečna ocena razpoloženja** : Pomaga vam razumeti splošno počutje vseh strank. Ocene občutkov so razvrščene v tri kategorije: 
  1.    Negativno (-5 > 2)
  2.    Nevtralno (-1 > 1)
  3.    Pozitivno (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualna predstavitev splošnega počutja strank.":::

- **Porazdelitev strank glede na oceno razpoloženja** : Stranke so razvrščene v negativne, nevtralne in pozitivne skupine glede na njihove ocene. Premaknite miškin kazalec nad vrstice v histogramu, da si ogledate število strank in povprečno oceno razpoloženja v vsaki skupini. Ti podatki vam lahko pomagajo [ustvariti segmente strank](segments.md) glede na njihove ocene razpoloženja.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="palični grafikon, ki prikazuje razpoloženje strank v treh skupinah razpoloženj.":::

- **Povprečna ocena razpoloženja skozi čas** : Razpoloženje strank se lahko sčasoma spremeni. Zagotavljamo trende v čustvih vaših strank za časovno obdobje vaših podatkov. Ta pogled vam lahko pomaga oceniti učinek sezonskih promocij, lansiranja izdelkov ali drugih časovno omejenih posegov na počutje strank. Oglejte si graf tako, da v spustnem meniju izberete leto zanimanja. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="grafikon zgodovine z oceno razpoloženja skozi čas, predstavljeno kot črta.":::
 
- **Razpoloženje med poslovnimi vidiki** : Ta tabela navaja povprečno razpoloženje po poslovnih vidikih. Lahko vam pomaga oceniti, kateri vidiki vašega podjetja že zadovoljujejo stranke ali vidiki, ki zahtevajo več pozornosti. Zapisi povratnih informacij, ki se ne ujemajo z nobenim od podprtih poslovnih vidikov, so razvrščeni pod **Drugo**. Tabela je privzeto razvrščena po abecedi. Razvrščanje lahko spremenite tako, da izberete glavo tabele.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Seznam poslovnih vidikov s povezanim vrednost mnenja in številom strank, ki ga omenjajo.":::
 
  Izberite ime poslovnega vidika, če si želite ogledati dodatne informacije, kako model prepozna poslovni vidik. V tem podoknu sta dva dela: 

  - **Vplivne besede** : prikazuje glavne besede, ki so vplivale na identifikacijo poslovnega vidika modela AI v povratnih informacijah strank. 
    **Pokažite žaljive besede** : Omogoča vam, da na seznam vključite žaljive besede iz izvirnih podatkov o povratnih informacijah strank. Privzeto je izklopljen.  Prikrivanje žaljivih besed poganja model AI in morda ne zazna vseh žaljivih besed. Nadaljujemo s ponavljanjem in usposabljanjem klasifikatorja za optimalno delovanje. Če zaznate žaljivo besedo, ki ni bila filtrirana po pričakovanjih, nas obvestite. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Seznam vplivnih besed s preklopom za prikaz ali skrivanje žaljivih besed.":::
 
  - **Vzorci povratnih informacij** : prikazuje dejanske zapise povratnih informacij v vaših podatkih. Besede so barvno označene glede na njihov vpliv na identifikacijo poslovnega vidika. 


### <a name="influential-words-analysis-tab"></a>Kartica za analizo vplivnih besed

Obstajajo trije razdelki dodatnih informacij, ki pojasnjujejo, kako deluje model razpoloženja.
  
1. **Glavne besede, ki prispevajo k pozitivnemu počutju** : prikazuje glavne besede, ki so vplivale na identifikacijo pozitivnega počutja modela AI v povratnih informacijah strank.  
2. **Glavne besede, ki prispevajo k negativnim čustvom** : prikazuje glavne besede, ki so vplivale na identifikacijo negativnega čustva modela AI v povratnih informacijah strank.  
3. **Vzorci povratnih informacij** : prikazuje dejanske zapise povratnih informacij, enega z negativnim mnenjem in enega s pozitivnim. Besede v zapisih povratnih informacij so označene glede na njihov prispevek k dodeljeni oceni razpoloženja. Besede, ki prispevajo k pozitivni oceni, so označene z zeleno. Besede, ki prispevajo k negativnemu rezultatu, so označene z rdečo.
   Izberite **Poglej več** naložiti več vzorcev povratnih informacij, ki zagotavljajo več informacij in konteksta o delovanju modela razpoloženja.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Primeri analize razpoloženja na podlagi povratnih informacij strank.":::
 
**Pokažite žaljive besede** : Omogoča vam, da na seznam vključite žaljive besede iz izvirnih podatkov o povratnih informacijah strank. Privzeto je izklopljen.  Prikrivanje žaljivih besed poganja model AI in morda ne zazna vseh žaljivih besed. Nadaljujemo s ponavljanjem in usposabljanjem klasifikatorja za optimalno delovanje. Če zaznate žaljivo besedo, ki ni bila filtrirana po pričakovanjih, nas obvestite. 

## <a name="act-on-analysis-results"></a>Delujte na podlagi rezultatov analize

Z izbiro lahko preprosto začnete ustvarjati nove segmente strank na strani z rezultati analize razpoloženja **Ustvarite segmente** na vrhu strani z rezultati modela.

:::image type="content" source="media/create-segment-model.png" alt-text="Ukazna vrstica z možnostmi na modelih predvidevanje.":::
 
## <a name="potential-bias"></a>Potencialna pristranskost

Kot pri vsaki funkciji, ki uporablja napovedno umetno inteligenco, se morate zavedati možne pristranskosti v podatkih, ki jih uporabljate za napovedovanje razpoloženja strank. Na primer, če povratne informacije zbirate samo digitalno, bi lahko zamudili povratne informacije strank, ki z vami predvsem poslujejo osebno, kar bi lahko vplivalo na rezultate funkcije.

Ker ta funkcija uporablja avtomatizirana sredstva za vrednotenje podatkov in predvidevanje na podlagi teh podatkov, se lahko uporablja kot metoda profiliranja, kot je ta izraz opredeljen v Splošni uredbi o varstvu podatkov ("GDPR"). Za uporabo te funkcije za obdelavo podatkov lahko veljajo načela splošne uredbe o varstvu podatkov ali drugi zakoni oz. predpisi. Odgovorni ste, da zagotovite, da uporabljate Dynamics 365 Customer Insights, vključno z analizo razpoloženja, je v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.

[!INCLUDE [footer-include](includes/footer-banner.md)]

