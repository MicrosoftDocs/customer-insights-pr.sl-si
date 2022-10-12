---
title: Predvidevanje priporočil za izdelke
description: Predvidite, katere izdelke bo stranka verjetno kupila ali imela z njimi interakcije.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610302"
---
# <a name="predict-product-recommendations"></a>Predvidevanje priporočil za izdelke

Model priporočil izdelkov ustvarja sklope predvidenih priporočil izdelkov. Priporočila temeljijo na predhodnem nakupovalnem vedenju in strankah s podobnimi vzorci nakupovanja. Ta model je za posamezne potrošnike (B-to-C).

Imeti morate poslovno znanje o različnih vrstah izdelkov za vaše podjetje in o tem, kako vaše stranke komunicirajo z njimi. Podpiramo priporočila izdelkov, ki so jih vaše stranke že kupile, ali priporočila za nove izdelke.

Za priporočila izdelkov lahko veljajo lokalni zakoni in predpisi ter pričakovanja kupcev; model ni posebej zasnovan za upoštevanje teh dejavnikov. zato **priporočila morate pregledati, preden jih posredujete svojim strankam** da zagotovimo, da upoštevate morebitne veljavne zakone ali predpise in pričakovanja strank glede tega, kar morda priporočate.

Rezultat tega modela ponuja priporočila na podlagi ID-ja izdelka. Vaš mehanizem dostave mora predvidene ID-je izdelkov preslikati v ustrezno vsebino, da lahko vaše stranke upoštevajo lokalizacijo, slikovno vsebino in drugo poslovno specifično vsebino ali vedenje.

> [!TIP]
> Preizkusite priporočilo za izdelek predvidevanje z uporabo vzorčnih podatkov: [Priporočilo izdelka predvidevanje vzorčni vodnik](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Zahteve

- Vsaj [sodelavec dovoljenja](permissions.md)
- Vsaj 100 strank, po možnosti več kot 10.000 strank.
- Identifikator stranke, enolični identifikator za povezovanje transakcij s posamezno stranko
- Vsaj eno leto podatkov o transakcijah, po možnosti dve do tri leta, da se vključi nekaj sezonskosti. V idealnem primeru vsaj tri ali več transakcij na ID stranke. Zgodovina transakcij mora vsebovati:
  - **Številka transakcije** : Enolični identifikator nakupa ali transakcije.
  - **Datum transakcije** : Datum nakupa ali transakcije.
  - **Vrednost transakcije** : Številčna vrednost nakupa ali transakcije.
  - **Edinstven ID izdelka** : ID kupljenega izdelka ali storitve, če so vaši podatki na ravni vrstične postavke.
  - **Nakup ali vračilo** : logična vrednost true/false kjer je *prav* identificira, da je bila transakcija vračilo. Če podatki o nakupu ali vračilu niso navedeni v modelu in **Vrednost transakcije** je negativen, sklepamo na donos.
- Podatkovna entiteta kataloga izdelkov za uporabo kot filter izdelkov.

> [!NOTE]
> - Model zahteva zgodovino transakcij vaših strank, pri čemer so transakcije kateri koli podatki, ki opisujejo interakcijo med uporabnikom in izdelkom. Na primer nakup izdelka, udeležba na tečaju ali obisk dogodka.
> - Konfigurirati je mogoče samo eno entiteto zgodovine transakcij. Če je nakupnih enot več, jih združite Power Query pred vnosom podatkov.
> - Če sta entiteti naročila in podrobnosti naročila različni, ju pred uporabo v modelu združite. Model ne deluje, če ima v entiteti samo ID naročila ali ID prejema.

## <a name="create-a-product-recommendation-prediction"></a>Ustvarjanje predvidevanja priporočil izdelkov

Izberite **Shrani osnutek** kadar koli shranite predvidevanje kot osnutek. Osnutek predvidevanje se prikaže v **Moje napovedi** zavihek.

1. Pojdi do **Inteligenca** > **Napovedi**.

1. Na **Ustvari** zavihek izberite **Uporabite model** na **Priporočila za izdelke (predogled)** ploščica.

1. Izberite **Začetek**.

1. **Poimenujte ta model** in **izhodno ime entitete**, da jih ločite od drugih modelov ali entitet.

1. Izberite **Naprej**.

### <a name="define-product-recommendation-preferences"></a>Določite nastavitve priporočil za izdelke

1. Nastavite **Število izdelkov** priporočiti stranki. Ta vrednost je odvisna od tega, kako način dostavljanja izpolnjuje podatke.

1. Izberite, ali želite vključiti izdelke, ki so jih kupci že kupili v **Pričakovani ponovni nakupi** polje.

1. Nastavite **Poglej nazaj okno** z časovni okvir model upošteva, preden ponovno priporoči izdelek uporabniku. Napišite na primer, da stranka kupi prenosnik vsaki dve leti. Model si ogleda zgodovino nakupov za zadnji dve leti in če najde artikel, se ta izloči iz priporočil.

1. Izberite **Naprej**

### <a name="add-purchase-history"></a>Dodajanje zgodovine nakupov

1. Izberite **Dodajte podatke** za **Zgodovina transakcij strank**.

1. Izberite vrsto semantične dejavnosti **SalesOrderLine** ki vsebuje zahtevane informacije o zgodovini transakcij ali nakupov. Če dejavnost ni nastavljena, izberite **tukaj** in ga ustvarite.

1. Spodaj **dejavnosti**, če so bili atributi dejavnosti semantično preslikani, ko je bila dejavnost ustvarjena, izberite določene atribute ali entiteto, na katero želite, da se osredotoči izračun. Če do semantične preslikave ni prišlo, izberite **Uredi** in preslikajte svoje podatke.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Stransko podokno prikazuje izbiro določenih dejavnosti pod semantično vrsto.":::

1. Izberite **Naslednji** in preglejte atribute, potrebne za ta model.

1. Izberite **Shrani**.

1. Izberite **Naprej**.

### <a name="add-product-information-and-filters"></a>Dodajte informacije o izdelku in filtre

Včasih so samo nekateri izdelki koristni ali primerni za vrsto predvidevanja, ki ga ustvarjate. Uporabite filtre izdelkov za identifikacijo podnabora izdelkov s posebnimi značilnostmi, ki jih priporočate svojim strankam. Model bo uporabil vse razpoložljive izdelke za učenje vzorcev, uporabil pa bo le izdelke, ki se ujemajo z rezultati filtra izdelka.

1. Dodajte svojo entiteto kataloga izdelkov, ki vsebuje informacije za vsak izdelek. Zemljevid zahtevanih informacij in izberite **Shrani**.

1. Izberite **Naprej**.

1. Izberite **Filtri izdelkov**:

   - **Brez filtrov**: uporabite vse izdelke v napovedi priporočila izdelka.

   - **Določitev posebnih filtrov izdelka**: uporabite določene izdelke v napovedi priporočila izdelka. V **Atributi kataloga izdelkov** podoknu izberite atribute iz entitete kataloga izdelkov, ki jih želite vključiti v filter.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Stransko podokno prikazuje atribute v entiteti kataloga izdelkov za izbiro filtrov izdelkov.":::

1. Izberite, ali želite uporabiti filter izdelka **in** oz **oz** da logično združite svoj izbor atributov iz kataloga izdelkov.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Vzorčna konfiguracija filtrov izdelkov v kombinaciji z logičnimi povezovalniki IN.":::

1. Izberite **Naprej**.

### <a name="set-update-schedule"></a>Nastavitev urnika posodobitev

1. Izberite pogostost za ponovno usposabljanje vašega modela. Ta nastavitev je pomembna za posodobitev točnosti napovedi, ko se v Customer Insights vnesejo novi podatki. Večina podjetij se lahko prekvalificira enkrat na mesec in pridobi dobro natančnost svojih predvidevanj.

1. Izberite **Naprej**.

### <a name="review-and-run-the-model-configuration"></a>Pregled in zagon konfiguracije modela

The **Pregled in zagon** korak prikazuje povzetek konfiguracije in nudi možnost spreminjanja, preden ustvarite predvidevanje.

1. Izberite **Uredi** na katerem koli od korakov za pregled in morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Shrani in zaženi** da začnete izvajati model. Izberite **Dokončano**. The **Moje napovedi** zavihek se prikaže med ustvarjanjem predvidevanje. Postopek lahko traja več ur, odvisno od količine podatkov, uporabljenih v predvidevanju.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Oglejte si predvidevanje rezultate

1. Pojdi do **Inteligenca** > **Napovedi**.

1. V **Moje napovedi** izberite predvidevanje, ki si ga želite ogledati.

Na strani z rezultati je pet primarnih razdelkov podatkov.

- **Zmogljivost modela:** Ocene A, B ali C označujejo uspešnost predvidevanje in vam lahko pomagajo pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Slika rezultata delovanja modela z oceno A.":::

  Ocene so določene na podlagi naslednjih pravil:
  - **A** ko je metrika »Uspeh @ K« vsaj 10 % višja od osnovne vrednosti.
  - **B** ko je metrika »Uspeh @ K« 0 % do 10 % višja od osnovne vrednosti.
  - **C** ko je metrika »Uspeh @ K« manjša od osnovne vrednosti.
  - **Izhodišče** : najbolj priporočeni izdelki glede na nakup štejejo za vse stranke + naučena pravila, ki jih identificira model = nabor priporočil za stranke. Napovedi se nato primerjajo z najboljšimi izdelki, določenimi s številom kupcev, ki so kupili izdelek. Če ima stranka v priporočenih izdelkih vsaj en izdelek, ki je bil viden tudi med najbolj kupljenimi izdelki, se stranka šteje za del osnovnega modela. Na primer, če je 10 od teh kupcev kupilo priporočen izdelek od 100 vseh kupcev, je izhodišče 10 %.
  - **Uspeh @ K** : Priporočila so ustvarjena za vse stranke in primerjana s potrditvenim nizom časovnega obdobja transakcij. Na primer, v 12-mesečnem obdobju je 12. mesec določen kot nabor podatkov za preverjanje veljavnosti. Če model predvideva vsaj en izdelek, ki ga kupite v 12. mesecu, na podlagi tega, kar se je naučil v preteklih 11 mesecih, bi ta kupec povečal vrednost metrike "Success @ K".

- **Najpogosteje predlagani izdelki (s skupnim številom):** pet najboljših izdelkov, ki so bili predvideni za vaše stranke.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graf, ki prikazuje 5 najbolj priporočenih izdelkov.":::

- **Ključni dejavniki priporočanja:** model uporablja zgodovino transakcij strank za podajanje priporočil izdelkov. Vzorce oblikuje na podlagi preteklih nakupov in ugotovi podobnosti med strankami in izdelki. Te podobnosti se nato uporabijo za oblikovanje priporočil izdelkov.
  Naslednji dejavniki lahko vplivajo na priporočilo izdelka, ki ga ustvari model.
  - **Pretekle transakcije** : Priporočen izdelek je temeljil na preteklih vzorcih nakupovanja. Model lahko na primer priporoči *Surface Arc Mouse*, če je nekdo pred kratkim kupil *Surface Book 3* in *Surface Pen*. Model se je naučil, da je v preteklosti veliko kupcev kupilo *Surface Arc Mouse* po nakupu *Surface Book 3* in *Surface Pen*.
  - **Podobnost strank**: priporočeni izdelek so v preteklosti kupile druge stranke, ki kažejo podobne vzorce nakupovanja. Mehanizem je Janezu na primer priporočil *Surface Headphones 2*, ker sta Daša in Branko pred kratkim kupila *Surface Headphones 2*. Model verjame, da je Janez podoben Daši in Branku, ker sta v preteklosti imela podobne vzorce nakupovanja.
  - **Podobnost izdelka**: priporočeni izdelek je podoben drugim izdelkom, ki jih je stranka že kupila. Model meni, da sta si dva izdelka podobna, če sta bila kupljena skupaj ali so ju kupile podobne stranke. Nekdo lahko na primer prejme priporočilo za *USB Storage Drive*, ker je prej kupil *USB-C to USB Adapter* in model verjame, da je *USB Storage Drive* podoben izdelku *USB-C to USB Adapter* na podlagi zgodovinskih vzorcev nakupovanja.

  Na vsako priporočilo izdelka vpliva eden ali več dejavnikov. Delež priporočil, kjer je vsak vplivni dejavnik igral svojo vlogo, je prikazan v grafikonu. V naslednjem primeru so na 100 % priporočil vplivale pretekle transakcije, na 60 % podobnost strank in na 22 % podobnost izdelkov. Premaknite kazalec miške nad stolpce na grafikonu, da vidite natančen delež prispevanja vplivnih dejavnikov.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Ključni faktorji priporočil, ki se jih je naučil model za ustvarjanje priporočil za izdelke.":::

- **Podatkovna statistika** : Pregled števila transakcij, strank in izdelkov, ki jih je model upošteval. Temelji na vhodnih podatkih, ki so bili uporabljeni za učenje vzorcev in ustvarjanje priporočil izdelkov.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Podatkovna statistika okoli vhodnih podatkov, ki jih model uporablja za učenje vzorcev.":::
  
  Model uporablja vse razpoložljive podatke za učenje vzorcev. Če torej v konfiguraciji modela uporabljate filtriranje izdelkov, ta razdelek prikazuje skupno število izdelkov, ki jih je model analiziral za učenje vzorcev, kar se lahko razlikuje od števila izdelkov, ki ustrezajo definiranim kriterijem filtriranja. Filtriranje velja za izhod, ki ga ustvari model.

- **Primeri priporočil za izdelke:** Vzorec priporočil, za katera model meni, da jih bo stranka verjetno kupila. Če je dodan katalog izdelkov, se ID-ji izdelkov nadomestijo z imeni izdelkov.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Seznam, ki prikazuje predloge z visoko zanesljivostjo za izbrani nabor posameznih strank.":::

> [!NOTE]
> V izhodni entiteti za ta model *rezultat* prikazuje kvantitativno mero priporočila. Model priporoča izdelke z višjo oceno pred izdelki z nižjo oceno. Če si želite ogledati rezultat, pojdite na **podatki** > **Entitete** in si oglejte podatkovni zavihek za izhodno entiteto, ki ste jo definirali za ta model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
