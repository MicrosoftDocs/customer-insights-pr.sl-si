---
title: Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke
description: Uporabite ta vzorčni priročnik, da preizkusite model za predvidevanje vrednosti življenjske dobe stranke.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129965"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke (CLV)

Ta priročnik vam bo z vzorčnimi podatki v celoti razložil primer predvidevanja vrednosti življenjske dobe stranke (CLV) v Customer Insights.

## <a name="scenario"></a>Scenarij

Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne aparate. Izdelke prodajajo prek svoje spletne strani Contoso Coffee. Podjetje želi predvideti vrednost (prihodek), ki jo lahko njihove stranke ustvarijo v naslednjih 12 mesecih. Poznavanje pričakovane vrednosti njihovih strank v naslednjih 12 mesecih jim pomaga usmeriti svoja tržna prizadevanja na stranke z visoko vrednostjo.

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja za sodelavca](permissions.md) v vpogledih občinstva.
- Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. opravilo – vnos podatkov

Preglejte članke [o vnosu podatkov](data-sources.md) in [uvozu virov podatkov s konektorji Power Query](connect-power-query.md). Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Vnos podatkov o strankah s platforme elektronskega poslovanja

1. Ustvarite vir podatkov z imenom **eCommerce**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Med urejanjem podatkov izberite **Pretvori** in nato **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **CreatedOn**: datum/čas/časovni pas

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**.

1. **Shranite** vir podatkov.

### <a name="ingest-online-purchase-data"></a>Vnos podatkov o spletnem nakupu

1. Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**. Znova izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za podatke **Spletni nakupi** https://aka.ms/ciadclassonline.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **PurchasedOn**: datum/čas
   - **TotalPrice**: valuta

1. V stranskem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **NakupiEPoslovanja**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Vnos podatkov o strankah iz sheme za zvestobo

1. Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:
   - **DateOfBirth**: datum
   - **RewardsPoints**: celo število
   - **CreatedOn**: datum/čas

1. V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.

1. **Shranite** vir podatkov.

### <a name="ingest-customer-data-from-website-reviews"></a>Vnesite podatke o strankah iz ocen spletnih mest

1. Ustvarite vir podatkov z imenom **Spletno mesto**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.

1. Vnesite URL za stike za elektronsko poslovanje https://aka.ms/CI-ILT/WebReviews.

1. Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.

1. Posodobite vrsto podatkov za spodaj navedene stolpce:

   - **ReviewRating**: decimalno število
   - **ReviewDate**: datum

1. V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** na **Ocene**.

1. **Shranite** vir podatkov.

## <a name="task-2---data-unification"></a>2. opravilo – poenotenje podatkov

Po uvozu podatkov se začne postopek poenotenja podatkov za ustvarjanje enotnega profila stranke. Če želite več informacij, glejte [Poenotenje podatkov](data-unification.md).

### <a name="map"></a>Preslikava

1. Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov. Izberite **Podatki** > **Poenotenje** > **Preslikava**.

1. Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**. Nato izberite **Uporabi**.

   ![Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.](media/unify-ecommerce-loyalty.png)

1. Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.

   ![Poenotite IDzvestobe kot primarni ključ.](media/unify-loyaltyid.png)

1. Izberite **Shrani**.

### <a name="match"></a>Povezovanje

1. Izberite zavihek **Ujemanje** in izberite **Nastavi vrstni red**.

1. Na spustnem seznamu **Primarno** izberite **StikiEPoslovanja: EPoslovanje** kot primarni vir in vključite vse zapise.

1. Na spustnem seznamu **Entiteta 2** izberite **zvesteStranke: ShemaZvestobe** in vključite vse zapise.

   ![Poenotenje ujemanja elektronskega poslovanja in zvestobe.](media/unify-match-order.png)

1. Izberite **Dodaj pravilo**

1. Dodajte svoj prvi pogoj z možnostjo FullName.

   - Za StikiEPoslovanja izberite **FullName** v spustnem meniju.
   - Za zvesteStranke izberite **FullName** v spustnem meniju.
   - Izberite spustni meni **Normaliziraj** in izberite **Vrsta (telefon, ime, naslov, ...)**.
   - Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.

1. Vnesite ime **FullName, Email** za novo pravilo.

   - Dodajte drugi pogoj za e-poštni naslov tako, da izberete **Dodaj pogoj**.
   - Za StikiEPoslovanja entitete izberite **E-pošta** v spustnem meniju.
   - Za zvesteStranke entitete izberite **E-pošta** v spustnem meniju.
   - Pustite polje Normaliziraj prazno.
   - Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.

   ![Poenotenje pravila ujemanja za ime in e-pošto.](media/unify-match-rule.png)

1. Izberite **Dokončano**.

1. Izberite **Shrani** in **Zaženi**.

### <a name="merge"></a>Spajanje

1. Odprite zavihek **Spajanje**.

1. Pri **IDstranke** za entiteto **zvesteStranke** spremenite prikazno ime v **ZVESTOBAIDstranke**, da se razlikuje od ostalih vnesenih ID-jev.

   ![Preimenujte ID stika iz ID-ja zvestobe.](media/unify-merge-contactid.png)

1. Izberite **Shrani** in **Zaženi združevanje in postopke iz strežnika**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>3. naloga – Konfiguriranje predvidevanja vrednosti življenjske dobe stranke

Z vzpostavljenimi poenotenimi profili strank lahko zaženemo predvidevanje vrednosti življenjske dobe stranke. Za podrobne korake glejte [Predvidevanje vrednosti življenjske dobe stranke (predogledna različica)](predict-customer-lifetime-value.md).

1. Odprite **Obveščanje**  > **Napovedi** in izberite **Model za izračun vrednosti življenjske dobe stranke**.

1. Preglejte informacije v stranskem podoknu in izberite **Začetek**.

1. Model poimenujte **Predvidevanje CLV OOB eCommerce**, izhodno entiteto pa **OOBeCommerceCLVPrediction**.

1. Določite nastavitve modela za model CLV:
   - **Časovno obdobje predvidevanja**: **12 mesecev ali 1 leto**. Ta nastavitev določa, kako daleč v prihodnost lahko napovemo vrednost življenjske dobe stranke.
   - **Dejavne stranke**: navedite, kaj dejavne stranke pomenijo vašemu podjetju. Nastavite zgodovinski časovni okvir, v katerem je morala stranka imeti vsaj eno transakcijo, da se je štela za dejavno. Model bo življenjsko vrednost stranke napovedal samo za aktivne stranke. Izberite možnost, po kateri model izračuna časovno obdobje na podlagi preteklih podatkov o transakcijah, ali pa določite časovni okvir V tem vzorčnem priročniku smo izbrali, **naj model izračuna interval nakupov**, kar je privzeta možnost.
   - **Stranke z visoko vrednostjo**: stranke z visoko vrednostjo opredelite kot percentil strank, ki največ zapravijo. Model uporablja te vhodne podatke za zagotavljanje rezultatov, ki ustrezajo vaši poslovni definiciji strank z visoko vrednostjo. Izberete lahko, naj model določi stranke z visoko vrednostjo. Pri tem je uporabljeno hevristično pravilo, ki izpelje percentil. Stranke z visoko vrednostjo lahko opredelite tudi kot percentil strank, ki bodo največ zapravile. V tem vzorčnem priročniku ročno definiramo stranke z visoko vrednostjo kot **zgornjih 30 % dejavnih strank, ki največ zapravijo** in izberite **Naprej**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak nastavitev v vodeni izkušnji za model CLV.":::

1. V koraku **Zahtevani podatki** izberite **Dodajanje podatkov**, da zagotovite podatke o zgodovini transakcij.

1. Dodajte entiteto **eCommercePurchases : eCommerce** in preslikajte atribute, ki jih zahteva model:
   - ID transakcije: eCommerce.eCommercePurchases.PurchaseId
   - Datum transakcije: eCommerce.eCommercePurchases.PurchasedOn
   - Znesek transakcije: eCommerce.eCommercePurchases.TotalPrice
   - ID izdelka: eCommerce.eCommercePurchases.ProductId

1. Izberite **Naprej**.

1. Nastavitev odnosa med entiteto **eCommercePurchases : eCommerce** in **eCommerceContacts : eCommerce**.

1. V koraku **Dodatni podatki (izbirno)** lahko dodate več podatkov o dejavnosti stranke. Ti podatki vam lahko pomagajo pridobiti več vpogledov v interakcije strank z vašim podjetjem, kar lahko prispeva k CLV. Z dodajanjem ključnih interakcij strank, kot so spletni dnevniki, dnevniki storitev za stranke ali zgodovina podeljevanja nagrad, lahko izboljšate natančnost predvidevanja. Izberite **Dodajanje podatkov**, da vključite več podatkov o dejavnostih strank.

1. Dodajte entiteto dejavnosti stranke in preslikajte imena polj v ustrezna polja, ki jih zahteva model:
   - Entiteta dejavnosti stranke: Reviews:Website
   - Primarni ključ: Website.Reviews.ReviewId
   - Časovni žig: Website.Reviews.ReviewDate
   - Dogodek (ime dejavnosti): Website.Reviews.ActivityTypeDisplay
   - Podrobnosti (znesek ali vrednost): Website.Reviews.ReviewRating

1. Izberite **Naprej** in konfigurirajte dejavnost in odnos med podatki o transakciji in podatki o stranki:  
   - Vrsta dejavnosti: izberite obstoječo
   - Oznaka dejavnosti: Pregled
   - Ustrezna nalepka: Website.Reviews.UserID
   - Entiteta stranke: eCommerceContacts:eCommerce
   - Odnos: WebsiteReviews

1. Izberite **Naprej** za nastavitev urnika modela.

   Model mora redno trenirati, da se nauči novih vzorcev, ko so vneseni novi podatki. Za ta primer izberite **Mesečno**.

1. Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.

## <a name="task-4---review-model-results-and-explanations"></a>4. opravilo – preglejte rezultate modela in razlage

Model naj dokonča usposabljanje in ocenjevanje podatkov. Nato lahko pregledate rezultate in razlage modela CLV. Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>5. naloga – Ustvarite segment strank z visoko vrednostjo

Z zagonom modela boste ustvarili novo entiteto, ki je navedena na zavihku **Podatki** > **Entitete**. Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment za stranko.

1. Izberite **Segmenti**. 

1. Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**.

   ![Ustvarjanje segmenta z izhodnimi podatki modela.](media/segment-intelligence.png)

1. Izberite entiteto **OOBeCommerceCLVPrediction** in definirajte segment:
  - Polje: CLVScore
  - Operator: večje kot
  - Vrednost: 1500

1. Izberite **Pregled** in **Shrani**, da shranite segment.

Zdaj imate segment, ki določa stranke, ki naj bi v naslednjih 12 mesecih ustvarile več kot 1500 $ prihodka. Ta segment se dinamično posodablja, če je vnesenih več podatkov.

Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).
