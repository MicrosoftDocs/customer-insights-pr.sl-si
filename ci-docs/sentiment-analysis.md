---
title: Analizirajte razpoloženje za povratne informacije strank (predogled)
description: Naučite se uporabljati model analize razpoloženja za povratne informacije strank v Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610486"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizirajte razpoloženje v povratnih informacijah strank (predogled)

Analiza razpoloženja vam omogoča, da sintetizirate razpoloženja strank in prepoznate poslovne vidike kot priložnosti za izboljšave. Ta funkcija Customer Insights vam pomaga razumeti, kaj deluje dobro in kaj morate obravnavati. Pomaga vam lahko pri spodbujanju poslovnih dejanj, ki omogočajo izkušnje, katerih rezultat je visoko zadovoljstvo in zvestoba strank.

## <a name="overview"></a>Pregled

Funkcija analize razpoloženja ustvari dva izpeljana vpogleda na ID stranke. Ocena razpoloženja (od -5 do 5) in seznam ustreznih poslovnih vidikov (področij poslovanja), ki vam skupaj pomagajo bolje razumeti povratne informacije strank.

Ta analiza vam pomaga:
- Pridobite pregled nad občutki strank do blagovne znamke ali organizacije
- Prepoznajte stranke z negativnim razpoloženjem, da osredotočite svoje akcije in dejavnosti ter optimizirate za večji donos  
- Prepoznajte poslovne vidike s težavami, na katere so opozorile stranke  
- Segmentirajte stranke na podlagi njihovega občutka za vodenje prilagojenih oglaševalskih akcij s ciljno usmerjeno prodajo, trženjem in podporo.
- Optimizirajte poslovanje tako, da obravnavate problematična področja ali priložnosti, ki so jih omenile stranke
- Prepoznajte poslovne vidike, ki jim gre dobro, in nagradite zadovoljne stranke prek programov zvestobe in promocije

Model nudi seznam besed, ki so vplivale na odločitev modela, da komentarjem povratnih informacij dodeli določeno oceno občutka ali poslovni vidik.  

Uporabljamo dva **Modeli obdelave naravnega jezika (NLP).** : Prvi vsakemu komentarju povratne informacije dodeli oceno občutka. Drugi model povezuje vsako povratno informacijo z vsemi uporabnimi poslovnimi vidiki. Modeli se usposabljajo na javnih podatkih iz virov v družabnih medijih, maloprodaji, restavracijah, potrošniških izdelkih in avtomobilski industriji.
  
Vnaprej določeni poslovni vidiki, ki jih model povezuje s povratnimi podatki, vključujejo:
- Upravljanje računa
- Dokončanje nakupa in plačilo
- Podpora za stranke
- Prevzem v trgovini
- Dostava in pridobivanje embalaže
- Prednaročilo
- Cena
- Zasebnost in varnost
- Promocije in nagrade
- Prevzem in garancija
- Zamenjava z vračilom in preklic
- Točnost izpolnjevanja
- Kakovost spletnega mesta/aplikacije

> [!NOTE]
> Trenutno podpiramo samo analizo razpoloženja na podlagi povratnih informacij strank v angleščini. V prihodnosti bo podprtih več jezikov. Če so naložene povratne informacije v drugih jezikih, bo model vseeno vrnil rezultate. Vendar ti rezultati ne bodo točni.

## <a name="prerequisites"></a>Zahteve

- Vsaj [sodelavec dovoljenja](permissions.md)
- [Poenoteno](data-unification.md) besedilni povratni podatki. Zelo vam priporočamo, da [konfigurirajte svoje entitete povratnih podatkov kot entitete dejavnosti semantičnega tipa](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (vrsta povratne informacije).
- Poenoteni ID stranke (UCID) iz poenotenja podatkov za ujemanje podatkovnih zapisov s povratnimi besedili za posamezno stranko.
- ID povratnih informacij
- Časovni žig povratne informacije
- Besedilo povratnih informacij

Customer Insights lahko obdela do 10 milijonov zapisov povratnih informacij za en model. Model lahko analizira povratne komentarje do 128 besed. Če je povratni komentar daljši, analiza upošteva le prvih 128 besed.

> [!NOTE]
> Konfigurirati je mogoče samo eno povratno entiteto. Če je povratnih entitet več, jih združite Power Query pred vnosom podatkov.

## <a name="configure-a-sentiment-analysis"></a>Konfigurirajte analizo razpoloženja

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Analiza razpoloženja strank (predogled)** ploščica.

1. Izberite **Začetek**.

1. **Ime** analizo in zagotovite **Ime izhodne entitete poslovnega vidika** in **Ime izhodne entitete ocene razpoloženja**.

1. Izberite **Naprej**.

1. Izberite **Dodajte podatke** za **Povratne informacije strank**.

1. Izberite vrsto semantične dejavnosti **Povratne informacije** ki vsebuje povratne podatke. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Korak konfiguracije za izbiro dejavnosti povratnih informacij za analizo razpoloženja.":::

1. Izberite dejavnosti, ki jih želite uporabiti za to analizo razpoloženja, nato izberite **Naslednji**.

1. Preslikajte atribute v svojih podatkih v atribute modela. 

1. Izberite **Shrani**.

1. Izberite **Naprej**. The **Pregled in zagon** korak prikazuje povzetek konfiguracije in ponuja možnost, da naredite spremembe, preden ustvarite analizo.

1. Izberite **Uredi** na katerem koli od korakov za pregled in morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Shrani in zaženi** da začnete izvajati model. Izberite **Dokončano**. The **Moje napovedi** zavihek se prikaže med ustvarjanjem predvidevanje. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Oglejte si rezultate analize

1. Pojdi do **Inteligenca** > **Napovedi**.

1. V **Moje napovedi** izberite predvidevanje, ki si ga želite ogledati.

Obstajata dva zavihka z rezultati.

### <a name="sumary-tab"></a>Zavihek Povzetek

Na strani z rezultati so štirje primarni razdelki podatkov.

- **Povprečna ocena razpoloženja** : Ocene razpoloženja vam pomagajo razumeti splošno razpoloženje vseh strank.
  - **Negativno** (-5 > 2)
  - **Nevtralno** (-1 > 1)
  - **Pozitivno** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualna predstavitev splošnega občutka stranke.":::

- **Porazdelitev strank glede na oceno razpoloženja** : Stranke so razvrščene v negativne, nevtralne in pozitivne skupine glede na njihovo razpoloženje. Premaknite miškin kazalec nad stolpce v histogramu, da vidite število strank in povprečno oceno razpoloženja v vsaki skupini. Ti podatki vam lahko pomagajo [ustvarite segmente strank](prediction-based-segment.md) na podlagi njihovih rezultatov razpoloženja.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="palični grafikon prikazuje razpoloženje strank v treh skupinah razpoloženj.":::

- **Povprečna ocena razpoloženja skozi čas** : Razpoloženje strank se lahko sčasoma spremeni. Zagotavljamo trende v občutkih vaših strank za časovni razpon vaših podatkov. Ta pogled vam pomaga oceniti učinek sezonskih promocij, lansiranj izdelkov ali drugih časovno omejenih posegov na razpoloženje strank. Oglejte si graf tako, da v spustnem meniju izberete leto zanimanja.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="grafikon zgodovine z rezultatom razpoloženja skozi čas, predstavljenim kot črta.":::

- **Razpoloženje v poslovnih vidikih** : povprečno razpoloženje po poslovnih vidikih vam pomaga oceniti, kateri vidiki vašega podjetja že zadovoljujejo stranke ali zahtevajo več pozornosti. Zapisi povratnih informacij, ki se ne ujemajo z nobenim od podprtih poslovnih vidikov, so razvrščeni pod **drugo**. Razvrstite podatke tako, da izberete kateri koli stolpec.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Seznam poslovnih vidikov s pripadajočim vrednost mnenja in številom strank, ki to omenjajo.":::

  Izberite ime poslovnega vidika, da si ogledate, kako poslovni vidik identificira model:

  - **Vplivne besede** : Najboljše besede, ki so vplivale na identifikacijo poslovnega vidika modela AI v povratnih informacijah strank.
    **Pokažite žaljive besede** : Omogoča vam, da na seznam vključite žaljive besede iz izvirnih povratnih informacij strank. Privzeto je izklopljen.  Maskiranje žaljivih besed uporablja model AI in morda ne bo zaznalo vseh žaljivih besed. Če zaznate žaljivo besedo, ki ni bila filtrirana po pričakovanjih, nas obvestite.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Seznam vplivnih besed s preklopom za prikaz ali skrivanje žaljivih besed.":::

  - **Vzorci povratnih informacij** : Dejanski zapisi povratnih informacij v vaših podatkih. Besede so barvno kodirane glede na njihov vpliv na identifikacijo poslovnega vidika.

### <a name="influential-words-analysis-tab"></a>Zavihek za analizo vplivnih besed

Obstajajo trije razdelki dodatnih informacij, ki pojasnjujejo, kako deluje model občutka.
  
- **Vrhunske besede, ki prispevajo k pozitivnemu razpoloženju** : Najpogostejše besede, ki so vplivale na identifikacijo pozitivnega razpoloženja v povratnih informacijah strank v modelu AI.  

- **Najpogostejše besede, ki prispevajo k negativnim občutkom** : Najpogostejše besede, ki so vplivale na identifikacijo negativnega čustva v povratnih informacijah strank s strani modela AI.

- **Vzorci povratnih informacij** : Dejanski zapisi povratnih informacij, eden z negativnim občutkom in eden s pozitivnim občutkom. Besede v zapisih povratnih informacij so označene glede na njihov prispevek k dodeljeni oceni občutka. Besede, ki prispevajo k pozitivni oceni razpoloženja, so označene z zeleno. Besede, ki prispevajo k negativni oceni, so označene z rdečo.
   Izberite **Poglej več** za nalaganje več vzorcev povratnih informacij.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Primeri analize razpoloženja glede povratnih informacij strank.":::

**Pokažite žaljive besede** : Omogoča vam, da na seznam vključite žaljive besede iz izvirnih povratnih informacij strank. Privzeto je izklopljen.  Maskiranje žaljivih besed uporablja model AI in morda ne bo zaznalo vseh žaljivih besed. Če zaznate žaljivo besedo, ki ni bila filtrirana po pričakovanjih, nas obvestite.

## <a name="act-on-analysis-results"></a>Delujte na podlagi rezultatov analize

Če želite iz rezultatov analize razpoloženja ustvariti nove segmente strank, izberite **Ustvarite segmente** na vrhu strani z rezultati modela.

## <a name="potential-bias"></a>Potencialna pristranskost

Kot pri vsaki funkciji, ki uporablja napovedno umetno inteligenco, lahko pride do potencialne pristranskosti podatkov, ki jih uporabljate za napovedovanje razpoloženja strank. Na primer, če povratne informacije zbirate samo digitalno, boste morda zamudili povratne informacije strank, ki v prvi vrsti poslujejo z vami osebno, kar vpliva na rezultate funkcije.

Ker ta funkcija uporablja avtomatizirana sredstva za ocenjevanje podatkov in izdelavo napovedi na podlagi teh podatkov, jo je zato mogoče uporabiti kot metodo profiliranja, kot je ta izraz opredeljen v Splošni uredbi o varstvu podatkov (»GDPR«). Za uporabo te funkcije za obdelavo podatkov lahko veljajo načela splošne uredbe o varstvu podatkov ali drugi zakoni oz. predpisi. Odgovorni ste za zagotovitev, da vaša uporaba Dynamics 365 Customer Insights, vključno z analizo razpoloženja, je v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacije.

[!INCLUDE [footer-include](includes/footer-banner.md)]

